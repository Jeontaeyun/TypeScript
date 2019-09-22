# JWT 토큰

## JWT \| JSON Web Token

 JWT는 JSON Web Token의 약자로 JSON 형태의 데이터를 저장하는 토큰입니다. JWT는 3 부분으로 구성되어 있습니다. 

| 구분  | 설명  |
| :--- | :--- |
| 헤더 HEADER | 토큰 종류와 해시 알고리즘 정보를 포함한 부분 |
| 페이로드 PAYLOAD | 토큰의 내용물이 인코딩된 부분 |
| 시그니처 SIGNATURE | 일련의 문자열, 시그니처를 통해 토큰이 변조되었는지 여부를 확인 가능 |

시그니처는 JWT 비밀키로 만들어지며, 이 비밀키가 노출되면 JWT 토큰을 위조할 수 있으므로 비밀키를 철저히 관리해야합니다. 시그니처 자체는 공개되어도 괜찮습니다.

#### JWT의 사용 이유

 JWT는 내용을 볼 수 있기 때문에 민감한 내용을 넣어서는 안됩니다. 이를 Decoding\(디코딩\)할 수 있어 PAYLOAD부분을 볼 수 있기 때문입니다. 

 JWT 토큰은 JWT 비밀키를 알지 않는 이상 변조가 불가능합니다. 변조한 토큰은 시그니처를 검사할 때 걸리게 됩니다. 변조할 수 없기 때문에 내용물을 믿고 사용할 수 있습니다.

#### JWT의 단점 

 JWT토큰은 용량이 크다는 단점이 있습니다. 매 요청 시 토큰이 오고 가기 때문에 데이터의 양이 증가합니다. 따라서 매번 사용자의 정보를 조회하는 방법이 더 비용이 큰지, JWT토큰을 사용해서 발생하는 데이터의 비용이 더 큰지 비교해 선택하면 됩니다. 

### JWT 발급하기

 JWT 토큰을 발급하기 위해서 **sign메서드**를 이용합니다.

```javascript
router.post('/token', async(req, res) => {
    try{
        const token = jwt.sign({
            id: req.body.user.id,
            nickname: req.body.user.nickname
        }, process.env.JWT_SECRET, {
            expiresIn : "1m",        // 유효기간
            issuer : "stark"         // 발급자
        });
        return res.json({
            code: 200,
            message: "토큰이 발급되었습니다.",
            token
    }
    catch(e){
        console.error(e);
        return res.status(500).json({
            code: 500,
            message: "서버 에러"
        });
    }
});
```



### JWT 사용하기

JWT는 JWT 모듈을 설치하여 사용할 수 있습니다.

```bash
$npm i jsonwebtoken
```

다른 사용자가 API를 쓰기 위해 JWT 토큰을 발급받고 인증 받아야 합니다. 이 부분은 대부분의 라우터에 공통되므로 미들웨어로 만들어 두는 것이 좋습니다 .

```text
//.env
JWT_SECRET = jwtSecret
```

JWT 비밀키는 .env 파일에서 보관하도록 합니다. 

```javascript
//middlewares.js
const jwt = require("jsonwebtoken");
...
exports.verifyToken = (req, res, next) => {
    try{
        // req.headers.authorization 요청 헤더에 저장된 토큰을 사용
        // 사용자가 쿠키처럼 헤더에 토큰을 넣어 보
        req.decoded = jwt.verify(req.headers.authoization, process.env.JWT_SECRET);
        return next();
    }
    catch(e){
        if(e.name === 'TokenExpiredError'){
            return res.status(419).json({ 
                code:419,
                message: "토큰이 만료되었습니다."
            });
        }
        return res.status(401).json({
            code: 401,
            message: "유효하지 않은 토큰입니다."
        })
    }
}
```

**jwt.verify**는 토큰을 검증하는 메서드입니다 .

### 클라이언트에서 토큰 보관

 서버 측에서 발급한 토큰을 클라이언트 측에서 보관하기 위해 다음과 같은 코드를 클라이언트 측에 작성해야 합니다. 

```javascript
if(!req.session.jwt){
    const tokenResult = await axios.post("http://토큰 발급 URL",{
        clientSecret = process.env.CLIENT_SECRET
    });
    if(tokenResult.data && tokenResult.data.code === 200){
        req.session.jwt = tokenResult.data.token;
        // 세션에 토큰 저장
    }
    else {
        return res.json(tokenResult.data);
        // 발급 실패 사유 응답
    }
}
```



