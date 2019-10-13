# connect-flash

## connect-flash

 connect-flash는 일회성 메세지들을 웹 브라우저에 나타낼 때 좋습니다. 다음과 같이 설치 후 사용할 수 있습니다. 

```bash
$npm i connect-flash
```

connect-flash는 cookie-parser와 express-session을 사용하므로 이들보다 뒤에 위치해야 합니다.

```javascript
...
const flash = require("connect-flash");
...
app.use(cookieparser(...));
app.use(session({
...
});
app.use(flash());
...
```

flash 미들웨어는 req 객체에 **req.flash\(키, 값\) 메서드를 추가**합니다. **req.flash\(키, 값\)으로 해당 키에 값을 설정**하고 **req.flash\(키\)로 해당 키에 대한 값을 불러옵니다**.

### connect-flash 예시

```javascript
const express = require("express");
const router = express.Router();

router.get('/', (req, res, next) => {
    res.send("respond with a resource");
});

router.get('/flash', (req, res, next) => {
    req.session.message = "세션 메세지";
    req.flash('message','flash메세지');
    req.redirect('/users/flash/result');    
});

router.get('/flash/result', (req, res, next) => {
    res.send(`${req.session.message} ${req.flash('message')}`
});
```

 위와 같이 구성할 경우 브라우저를 새로고침 하면 flash 메세지는  사라집니다. flash 메세지는 일회성이기 때문입니다.

 일회성 메세지라는 성질을 이용하여 **로그인 에러**나 **회원 가입 에러** 같은 **일회성 경고 메세지**를 처리하면 좋습니다.

