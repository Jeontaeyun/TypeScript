# ws 모듈 \| 웹 소켓 모듈

## 웹 소켓 ws 모듈

 노드에서 웹 소켓을 이용하기 위해서는 ws모듈을 이용해야 합니다. `$npm i ws` 를 통해 웹 소켓 모듈을 설치할 수 있습니다.

### 웹 소켓 로직 

```javascript
cosnt WebSocket = require('ws');

// 웹 소켓은 변수로 server를 받아 HTTP포트를 자동으로 공유합니다.
module.exports = (server) => {
    // server에 웹 소켓 서버를 연결한다.
    const wwsServer = new WebSocket.Server({server});
    
    // 서버와 클라이언트가 웹 소켓 연결을 맺을 때 connection 이벤트 발생
    wwsServer.on('connection', (ws, req)=>{
        //클라이언트의 IP를 알아내는 유명한 방법 중 하나
        const ip = req.headers['x-forwarded-for'] || req.connection.remoteAddress;
        console.log('새로운 클라이언트 접속',ip);
        // ws는 웹 소켓 객체이다. 여기에 이벤트 리스너 3개를 붙여준다.
        // 클라이언트로 부터 메세지가 왔을 때 발생
        ws.on('message', (message) => {
            console.log(message);
        });
        // 웹 소켓 연결 중 문제가 생겼을 때 발
        ws.on('error', (error) => {
            console.error(error);
        });
        // 클라이언트와 연결이 끊어졌을 때 발생
        ws.on('close', () => {
            console.log('클라이어너트 접속 해제', ip);
            // 메모리 누수를 위해서 setInterval clear
            clearInterval(ws.interval);
        });
        const interval = setInterval(()=>{
            if(ws.readyState === ws.OPEN){
                 //ws.send()를 통해서 message를 주고 받을 수 있다.
                 ws.sned('서버에서 클라이언트로 메세지를 보냅니다.');
            }
        },3000);
    });
}

```

### Express 와 웹 소켓 연결 

```javascript
const express = require('express');
(...)
const webSocket = require('./socket');
(...)
const server = app.listen(app.get('port'), () => {
    console.log(app.get('port'),'번 포트에서 대기 중');
});
// 웹 소켓 연결하기
webSocket(server);
```

### 클라이언트 웹 소켓 ws 모듈 사용 

 웹 소켓은 양 방향 통신이기 때문에 단순히 서버에서 설정한다고 작동하는 것이 아닙니다. 따라서, 클라이언트 측에도 다음과 같이 ws모듈의 설정을 해주어야 합니다.

```javascript
// 주소의 프로토콜이 ws인 것을 주의하자.
const webSocket = new WebSocket("ws://localhost:8005");
webSocket.onopen = function() {
    console.log('서버와 웹 소켓 연결 성공!');
}
webSocket.onmessage = function(event) {
    console.log(event.data);
    webSocket.send('클라이언트에서 서버로 답장을 보냅니다.');
}
```

### 웹  소켓

#### 웹  소켓의 4가지 상태 \| readyState

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">CONNECTING</td>
      <td style="text-align:left">&#xC6F9; &#xC18C;&#xCF13; &#xC5F0;&#xACB0;&#xC911;</td>
    </tr>
    <tr>
      <td style="text-align:left">OPEN</td>
      <td style="text-align:left">
        <p>&#xC6F9; &#xC18C;&#xCF13; &#xC5F4;&#xB9BC;</p>
        <p>&#xC774;&#xB54C;&#xB9CC; &#xC5D0;&#xB7EC; &#xC5C6;&#xC774; &#xBA54;&#xC138;&#xC9C0;&#xB97C;
          &#xBCF4;&#xB0BC; &#xC218; &#xC788;&#xC2B5;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">CLOSING</td>
      <td style="text-align:left">&#xC6F9; &#xC18C;&#xCF13; &#xB2EB;&#xB294; &#xC911;</td>
    </tr>
    <tr>
      <td style="text-align:left">CLOSED</td>
      <td style="text-align:left">&#xC6F9; &#xC18C;&#xCF13; &#xB2EB;</td>
    </tr>
  </tbody>
</table>####  이벤트 기반 동작

 웹 소켓은 이벤트 기반으로 동작하여 웹 소켓을 이용하는 서버측과 클라이언트 측에 이벤트 리스너 형태로 동작을 구현할 수 있습니다. 

