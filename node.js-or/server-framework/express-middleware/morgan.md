# morgan

## morgan

 **morgan 미들웨어는 요청에 대한 정보를 콘솔에 기록해주는 미들웨어**로 다음과 같이 사용합니다.

```javascript
...
const  logger = require("morgan");
...
app.use(logger("dev"));
...
```

함수의 인자로 다음의 값이 할당 가능합니다. 

| 구분  | 설명  |
| :--- | :--- |
| dev | \[ HTTP요청 \| 주소 \| HTTP 상태코드 \| 응답속도 \| 응답 바이트 \] 반환 |
| short |  |
| common |  |
| combined |  |

보통 **개발 시에는 short나 dev**를 많이 쓰고, **배포 시에는 common이나 combined**를 많이 사용합니다. 

 콘솔 뿐만 아니라 파일이나 데이터베이스에 로그를 남길 수도 있습니다. 하지만 이런 작업을 할 때는 **winston 모듈을 더 많이 사용**합니다. 

