# cookie-parser

## cookie-parser

 cookie-parser는 요청에 동봉된 쿠키를 해석해줍니다. 다음과 같이 사용할 수 있습니다.

```javascript
...
const cookieParser = require("cookie-parser");
...
app.use(cookieParser());
...
```

 해석된 쿠키들은 **req.cookies 객체**에 들어갑니다. 

예를 들어 name = stark 쿠키를 보내면 req.cookies는 { name : "stark" }가 됩니다. cookieParser에는 **첫 번째 인자로 문자열을 넣어줄 수 있는데 쿠키들은 제공한 문자열로 서명된 쿠키**가 됩니다. 

 **서명된 쿠키는 클라이언트에서 수정했을 때 에러가 발생하므로 클라이언트에서 쿠키로 위험한 행동을 하는 것으르 방지**할 수 있습니다. 

```javascript
app.use(cookieParser("secret key"));
```

