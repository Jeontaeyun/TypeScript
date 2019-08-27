# HTTP 통신

## HTTP \| HyperText Transfer Protocol

![Network Communication Layer](../../.gitbook/assets/image.png)

 인터넷에서 웹 서버와 사용자의 인터넷 브라우저 사이에 문서를 전송하기 위해 사용하는 통신 규약을 HTTP라고 한다. HTTP는 **80번 포트**를 사용하도록 정의되어 있다.

 HTTP서버로 부터 웹 정보를 얻기 위해서는 http://www.도메인.co.kr과 같이 URL 주소에 HTTP를 사용한다고 명시해야 한다. 

 이와 마찬가지로 FTP를 이용해서 서버에 접근하기 위해서는 ftp://www.도메인.co.kr로 텔넷\(Telnet\)을 이용하려면 telnet://www.도메인.co.kr로 주소를 명시해야 한다.

 HTTP는 Request\(요청\)과 Response\(응답\)으로 이루어진 통신 프로토콜이다. 

{% hint style="info" %}
\*\*\*\*[**HTTP와 HTTPs**](https://ko.wikipedia.org/wiki/HTTPS)\*\*\*\*

https로 접속하기 위해서는 별도의 도메인과 인증서 발급이 필요합니다. HTTP 프로토콜에 보안을 강화하기 위해 인증과 암호화를 추가한 프로토콜이다.

HyperText Protocol over Secure Socket Layer의 약자로 HTTPS는 소켓 통신에서 일반 텍스트를 사용하는 대신에, SSL이나 TLS프로콜을을 통해 세션 데이터를 암호화한다. 따라서 데이터의 적절한 보호를 보장한다. 

HTTPS의 기본 TCP/IP포트는 443이다. 
{% endhint %}

### HTTP 상태코드

#### 2xx \| 요청에 대한 응답 성공

| 구분  | 설명  |
| :--- | :--- |
| 200 | Success. 대부분의 성공 응답에 200분 상태 코드를 사하는 응답 코드 |
| 201 | Created. POST 메소드로 요청한다는 것은 서버에 자원 생성을 요청하는 의미인데 서버 쪽에서 자원 생성에 성공하면 201 상태 코드를 클라이언트로 응답하는 응답 코 |
| 204 | No Content. 서버에서 성공했는데 응답할 바디가 없을 경우 204 상태 코드를 반환할 때 응답코 |

#### 3xx \| 리다이렉션

| 구분  | 설명  |
| :--- | :--- |
| 301 | 영구 이동. 요청한 페이지를 새 위치로 영구적으로 이동할 때의 응답 코드 |
| 302 | 임시 이동. 현재 서버가 다른 위치의 페이지로 요청을 응답하고 있지만 요청자는 향후 요청시 원래 위치를 계속 사용하는 응답 코드  |
| 307 | 임시 리다이렉션. 현재 서버가 다른 위치의 페이지로 요청에 응답하고 있지만 요청자는 향후 요청시 원래 위치를 계속 사용하는 응답 코드  |

#### 4xx \| 클라이언트 요청 에러

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">400</td>
      <td style="text-align:left">Bad request. &#xD074;&#xB77C;&#xC774;&#xC5B8;&#xD2B8;&#xC5D0;&#xC11C;
        &#xD30C;&#xB77C;&#xBBF8;&#xD130;&#xB97C; &#xD3EC;&#xD568;&#xD558;&#xC5EC;
        &#xC11C;&#xBC84; API&#xB97C; &#xC694;&#xCCAD;&#xD558;&#xB294;&#xB370; &#xD30C;&#xB77C;&#xBBF8;&#xD130;&#xAC00;
        &#xC798;&#xBABB;&#xB418;&#xC5C8;&#xC744; &#xACBD;&#xC6B0; &#xC751;&#xB2F5;
        &#xCF54;&#xB4DC;</td>
    </tr>
    <tr>
      <td style="text-align:left">401</td>
      <td style="text-align:left">
        <p>Unauthorized. &#xC778;&#xC99D;&#xC774; &#xD544;&#xC694;&#xD55C; API&#xC5D0;
          &#xB300;&#xD574; &#xC778;&#xC99D;&#xB418;&#xC9C0; &#xC54A;&#xC740; &#xC694;&#xCCAD;&#xC77C;
          &#xACBD;&#xC6B0;&#xC758; &#xC751;&#xB2F5; &#xCF54;&#xB4DC;</p>
        <p>&#xC608;&#xB97C; &#xB4E4;&#xC5B4; OAuth&#xB97C; &#xC0AC;&#xC6A9;&#xD560;
          &#xB54C; &#xC561;&#xC138;&#xC2A4; &#xD1A0;&#xD070;(Access Token)&#xC774;
          &#xC720;&#xD6A8;&#xD558;&#xC9C0; &#xC54A;&#xC744; &#xACBD;&#xC6B0;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">403</td>
      <td style="text-align:left">Forbidden. &#xC811;&#xADFC; &#xAD8C;&#xD55C;&#xC774; &#xC5C6;&#xC744;
        &#xB54C; &#xBC1C;&#xC0DD;&#xD558;&#xB294; &#xC751;&#xB2F5; &#xCF54;&#xB4DC;</td>
    </tr>
    <tr>
      <td style="text-align:left">404</td>
      <td style="text-align:left">
        <p>Not Found. &#xC870;&#xD68C;&#xD560; &#xC790;&#xC6D0;&#xC774; &#xC11C;&#xBC84;&#xC5D0;
          &#xC5C6;&#xB294; &#xACBD;&#xC6B0;&#xC758; &#xC751;&#xB2F5; &#xCF54;&#xB4DC;</p>
        <p>&#xC6F9; &#xBE0C;&#xB77C;&#xC6B0;&#xC800;&#xB85C; &#xC5B4;&#xB5A4; &#xD398;&#xC774;&#xC9C0;&#xB97C;
          &#xCC3E;&#xC744; &#xB54C; &#xADF8; &#xD398;&#xC774;&#xC9C0;&#xAC00; &#xC5C6;&#xB294;
          &#xACBD;&#xC6B0; &#xBCF4;&#xD1B5; 404&#xD398;&#xC774;&#xC9C0;&#xB77C;&#xACE0;
          &#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">409</td>
      <td style="text-align:left">Conflict. &#xD074;&#xB77C;&#xC774;&#xC5B8;&#xD2B8;&#xC5D0;&#xC11C; POST
        &#xBA54;&#xC18C;&#xB4DC;&#xB85C; &#xC11C;&#xBC84;&#xC5D0;&#xAC8C; &#xC790;&#xC6D0;
        &#xCD94;&#xAC00;&#xB97C; &#xC694;&#xCCAD;&#xD588;&#xC744; &#xB54C; &#xC774;&#xBBF8;
        &#xADF8; &#xC790;&#xC6D0;&#xC774; &#xC11C;&#xBC84;&#xC5D0; &#xC788;&#xC744;
        &#xB54C;&#xC758; &#xC751;&#xB2F5; &#xCF54;&#xB4DC;</td>
    </tr>
  </tbody>
</table>#### 5xx \| 서버 응답 에

| 구분  | 설명  |
| :--- | :--- |
| 500 | 내부 서버 오류. 서버에 오류가 발생하여 요청을 수행할 수 없을 때 응답 코드 |
| 501 | 구현되지 않음. 서버에 요청을 수행할 수 있는 기능이 없을 때 응답 코드  |

