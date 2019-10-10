# HTTPs와 HTTP2

## HTTPS와 HTTP2

### HTTPS

 https모듈은 웹 서버에 SSL\(Secure Socket Layer\) 암호화를 추가하는 동작을 합니다. 

{% hint style="info" %}
**SSL**

SSL은 HTTP 프로토콜 상위에 통신시 서버-클라이언트간 통신을 할 때 클라이언트와 서버간 공유하는 암호화키를 가지고 암호화된 데이터가 송수신되는 방식입니다.
{% endhint %}

즉 HTTPS는 SSL 프로토콜 위에서 돌아가는 프로토콜을 의미합니다.

이를 통해 POST나 GET 요청을 할 때 오고가는 데이터를 암호화해서 중간에 다른 사람이 요청을 가로채더라도 내용을 확인할 수 없게 해줍니다. 

{% hint style="info" %}
**최근에는 로그인이나 결젝가 필요한 창에서 HTTPS 적용이 필수인 추세입니다.**
{% endhint %}

SSL을 도입하면 브라우저 주소창에 자물쇠 표시가 나타납니다. HTTPS서버는 다음과 같이 구현할 수 있습니다. 

```javascript
const https = require("https");
const fs = require("fs");

https.createServer({
    cert: fs.readFileSync("도메인 인증서 경로");
    key: fs.rreadFileSync("도메인 비밀키 경로");
    ca: [
        fs.readFileSync("상위 인증서 경로"),
        fs.readFileSync("상위 인증서 경로")
    ]
},(req, res) => {
    res.write("<h1>https 모듈</h1>");
    res.end("<p>암호화 된 서버입니다.</p>");
}).listen(443, () => {
    console.log("443번 포포트에서 서버 대기중 입니다.!");
});
```

https 모듈을 사용하기 위해서는 createServer의 첫번째 인자로 인증서에 관련된 옵션 객체를 넣어주어야 합니다. **인증서를 구입하면 pem이나 crt 또는 key 확장자를 가진 파일을 제공해줍니다.**  

### HTTP/2.0

 노드는 http2 모듈을 통해 SSL 암호화와 더불어 최신 HTTP 프로토콜인 HTTP/2.0 방식을 사용할 수 있게 해줍니다. 

http/2는 요청 및 응답 방식이 기존 http/1.1보다 개선되어 훨씬 효율적으로 요청을 보내어 웹 속도가 개선됩니다. 

 HTTP/2.0에는 Multiplexing이라는 개념이 도입되어 매우 속도가 빠르며 다음과 같이 구현할 수 있습니다. 

```javascript
const http2 = require("http2");
const fs = require("fs");

http2.createSecureServer({
    cert: fs.readFileSync("도메인 인증서 경로");
    key: fs.rreadFileSync("도메인 비밀키 경로");
    ca: [
        fs.readFileSync("상위 인증서 경로"),
        fs.readFileSync("상위 인증서 경로")
    ]
},(req, res) => {
    res.write("<h1>http/2.0 모듈</h1>");
    res.end("<p>암호화 된 http/2.0 서버입니다.</p>");
}).listen(443, () => {
    console.log("443번 포포트에서 서버 대기중 입니다.!");
})
```

