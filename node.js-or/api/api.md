# 사용량 제한

## express-rate-limit

 API서버를 운영할 때 JWT를 이용해 토큰을 발급 받은 사람만 API를 사용할 수 있게 필터링을 해도 과도한 API를 사용하는 것에 대한 대처는 할 수 없습니다. 

 이럴 때는 **express-rate-limit 패키지를 이용해 API를 사용할 수 있는 횟수를 제한**할 수 있습니다.

```bash
$npm i express-rate-limit
```

JWT 미들웨어에 다음과 같이 지정해줍니다.

```javascript
const jwt = require("jsonwebtoken");
const RateLimit = requie("express-rate-limit");
...
exports.apiLimiter = new RateLimit({
    windowMs: 60 * 1000,        // 기준시간
    max: 1,                     // 허용 횟수
    delayMs: 0,                 // 호출 가녁
    handler(req,res){           // 제한 초과시 핸들러 함수
        res.status(this.statusCode).json({
            conde: this.statusCode,
            message: "1분에 한 번만 요청할 수 있습니다."
        });
    }
});
```

| 응답코드 | 메세지 |
| :--- | :--- |
| 200 | JSON 데이터 입니다. |
| 401 | 유효하지 않은 토큰입니다. |
| 410 | 새로운 버전이 나왔습니다. 새로운 버전을 사용하세요 |
| 419 | 토큰이 만료되었습니다. |
| 429 | 1분에 한 번만 요청할 수 있습니다.  |

