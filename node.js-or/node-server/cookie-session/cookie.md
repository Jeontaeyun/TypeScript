# Cookie

## 쿠키란?

### 쿠키의 설명 및 특

 쿠키는 웹 서버의 정보를 웹 브라우저에 저장해서 **개인화**, **인증**, **사용자 추적**등이 가능 하도록 도와주는 HTTP의 개념입니다.

 웹이 사용화 된 후 웹 개발에서의 최고의 관심사는 개인화였습니다. 개인화란 모든 사람에게 같은 페이지를 보여주는 것이 아니고, 개인마다 각자의 페이지를 보여주는 것을 말합니다. 다음과 같은 예가 개인화의 대표적인 예시 입니다.

* 한 번 로그인하면 그 로그인이 유지되는 것
* 장바구니에 상품을 넣어두면 그 상품이 웹 사이트를 나가도 저장되는 것
* 지문 인증을 통해서 개인의 정보를 쉽게 불러오는 

위와 같은 예시를 통해서 쿠키의 장점을 나열하면 다음과 같습니다.

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>&#xAD6C;&#xBD84; </b>
      </th>
      <th style="text-align:left"><b>&#xC124;&#xBA85; </b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>&#xC138;&#xC158; &#xAD00;&#xB9AC; </b>
        </p>
        <p><b>Session Management</b>
        </p>
      </td>
      <td style="text-align:left">&#xC11C;&#xBC84;&#xC5D0; &#xC800;&#xC7A5;&#xD574;&#xC57C; &#xD560; &#xB85C;&#xADF8;&#xC778;,
        &#xC7A5;&#xBC14;&#xAD6C;&#xB2C8;, &#xAC8C;&#xC784; &#xC2A4;&#xCF54;&#xC5B4;
        &#xB4F1;&#xC758; &#xBCF4; &#xAD00;&#xB9AC;</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>&#xAC1C;&#xC778;&#xD654;</b>
        </p>
        <p><b>Personalization</b>
        </p>
      </td>
      <td style="text-align:left">&#xC0AC;&#xC6A9;&#xC790; &#xC120;&#xD638;, &#xD14C;&#xB9C8; &#xB4F1;&#xC758;
        &#xC138;&#xD305;</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>&#xD2B8;&#xB798;&#xD0B9;</b>
        </p>
        <p><b>Tracking</b>
        </p>
      </td>
      <td style="text-align:left">&#xC0AC;&#xC6A9;&#xC790; &#xD589;&#xB3D9;&#xC744; &#xAE30;&#xB85D;&#xD558;&#xACE0;
        &#xBD84;&#xC11D;&#xD558;&#xB294; &#xC6A9;&#xB3C4;</td>
    </tr>
  </tbody>
</table>### 쿠키의 생성 및 읽기

 쿠키를 Express에서 생성하기 위해서는 다음과 같이 생성할 수 있습니다.

```javascript
res.writeHead(200, {
	‘Set-Cookies’ : [‘yummy_cookie=choch’,’tasty_cookie=strawberry’],
	// ’<cookie-name>=<cookie-value>’ 의 형태로 Set-Cookies에 배열로 넣어준다.
});

```

 또한 `npm i cookie -save`를 통해 설치한 cookie API를 통해 손쉽게 쿠키를 읽을 수 있습니다.

```javascript
const cookie = require('cookie');
...
const cookies = cookie.parse(req.headers.cookie);
console.log(cookies);
```

 쿠키는 HTTP통신에서 Header부분에 기술되어 있습니다. 따라서 HTTP 통신간 쿠키를 확인하고 싶을 때는 header부분을 참조하면 됩니다.

### 쿠키의 종류

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Session Cookie</td>
      <td style="text-align:left">
        <p>&#xC6F9; &#xBE0C;&#xB77C;&#xC6B0;&#xC800;&#xB97C; &#xB044;&#xBA74; &#xC0AC;&#xB77C;&#xC9C0;&#xB294;
          &#xD718;&#xBC1C;&#xC131; &#xCFE0;&#xD0A4;</p>
        <p>&#x2018;Set-Cookies&#x2019; : &lt; Cookie-name &gt;=&lt; Cookie-value
          &gt;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Permanent Cookie</td>
      <td style="text-align:left">
        <p>&#xC6F9; &#xBE0C;&#xB77C;&#xC6B0;&#xC800;&#xB97C; &#xAEBC;&#xB3C4; &#xC0AC;&#xB77C;&#xC9C0;&#xC9C0;
          &#xC54A;&#xB294; &#xCFE0;&#xD0A4;</p>
        <p>&#x2018;Set-Cookies&#x2019; : &lt; Cookie-name &gt;=&lt; Cookie-value
          &gt;; Max-Age=${day},</p>
        <p>&#x2018;Set-Cookies&#x2019; : &lt; Cookie-name &gt;=&lt; Cookie-value
          &gt;; Expires=${day}</p>
      </td>
    </tr>
  </tbody>
</table>### 쿠키 옵션 

| 구분  | 설명  |
| :--- | :--- |
| **secure** | 웹 브라우저와 웹 서버가 https으로 통신하는 경우만 웹 브라우저가 쿠키를 서버로 전송하는 옵션. |
| **httpOnly** | 자바스크립트의 document.cookie를 이용해서 쿠키에 접속하는 것을 막기 위한 옵션. 쿠키를 훔쳐가는 것을 방지한다. |
| **Path** | path = ${path} 옵션을 통해 해당 디렉토리 하위 디렉토리서만 해당 쿠키가 존재하게 하는 옵션 |
| **Domain** | Domain= ${domain} 옵션을 통해 해당 도메인에서만 쿠키가 존재하게 하는 옵션 |

