# Socket.io 모듈

## Socket.it 모듈

 웹 소켓을 지원하지 않는 브라우저에서도 웹 소켓을 구현할 수 있도록 도와주며 웹 소켓을 이용한 실시간 데이터 처리에 유용한 기능을 담은 자바스크립트 라이브러리.

`$npm i socket.io` 를 통해서 설치 가능하고 다음과 같이 Socket.io의 설정을하고 Express와 연결합니다.

### Socket 설정 \| 서버

```javascript
const SocketIO = require('socket.io');

module.exports = (server) => {
    const io = SocketIO(server, {path:'/socket.io'});
    
    io.on('connection', (socket) => {
        const req = socket.request;
        const ip = req.headers['x-forwarrded-for'] || req.connection.remoteAddress;
        console.log('새로운 클라이언트 접속!', ip, socket.id, req.id);
        socket.on('disconnect', () => {
            console.log('클라이언트 접속 해제', ip, socket.id);
            clearInterval(socket.interval);
        });
        socket.on('error', (error) => {
            console.log(error);
            socket.on('reply', (data) => {
                console.log(data);
            });
        });
        // 3초 마다 news 이벤트를 발생시킨다.
        socket.interval = setInterval(()=> {
            socket.emit('news','Hello Socket.IO');
        },3000);
    });
}
```

 이때, 클라이언트 측과 서버 측의 path 설정이 같아야 Socket.io를 이용한 통신이 가능합니다. 

### Socket 설정 \| 클라이언트

```javascript
const socket = io.connect('http://localhost:8005', {
    path: '/socket.io',
    transports: ['websocket']
    // 위의 설정을 통해 폴링을 한 후가 아닌 처음 부터 바로 웹 소켓을 사용할 수 있다.
});
// news이벤트가 발생하면 데이터를 받아 console.log하고 reply이벤트를 전송한다.
socket.on('news', function (data) {
    console.log(data);
    socket.emit('reply', 'Hello Node.JS');
});
```

### Socket.IO

 Socekt.io는 ws 프로토콜이 아니라 http 프로토콜을 먼저 사용합니다. 즉, 폴링 방식으로 서버와 연결한 후 웹 소켓을 사용할 수 있다면 웹 소켓으로 연결합니다. 

 따라서, 웹 소켓을 지원하지 않는 브라우저는 폴링 방식으로, 웹 소켓을 지원하는 브라우저는 웹 소켓 방식으로 사용 가능한 것입니다.

### Socekt.IO의 네임스페이스 

### Socket.IO API

| 구분 | 설명  |
| :--- | :--- |
| socket.emit\('이벤트', data\) | 데이터를 전송하는 측에서 이벤트를 발생시키고 전송한다. |
| socket.on\('이벤트이름', function\(data\){...}\) | 데이터를 수신하는 측에서 이벤트 리스너를 등록합니다.  |

