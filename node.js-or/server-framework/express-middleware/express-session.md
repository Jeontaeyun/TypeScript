# express-session

## express-session

 **express-session은 세션 관리용 미들웨어**입니다. 로그인 등의 이유로 세션을 구현할 때 매우 유용합니다. 다음과 같이 사용합니다.

```bash
$npm i express-session
```

```javascript
...
const session = require("express-session");
...
app.use(session({
    reave: false,
    saveUninitailized: false,
    secret: "secret key",
    cookie: {
        httpOnly: true,
        secure: false
    }
}));
...
```

#### express-session 옵션 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">resave</td>
      <td style="text-align:left">&#xC694;&#xCCAD;&#xC774; &#xC654;&#xC744; &#xB54C; &#xC138;&#xC158;&#xC5D0;
        &#xC218;&#xC815; &#xC0AC;&#xD56D;&#xC774; &#xC0DD;&#xAE30;&#xC9C0; &#xC54A;&#xB354;&#xB77C;&#xB3C4;
        &#xC138;&#xC158;&#xC744; &#xB2E4;&#xC2DC; &#xC800;&#xC7A5;&#xD560;&#xC9C0;&#xC5D0;
        &#xB300;&#xD55C; &#xC124;&#xC815;</td>
    </tr>
    <tr>
      <td style="text-align:left">saveUninitailized</td>
      <td style="text-align:left">
        <p>&#xC138;&#xC158;&#xC5D0; &#xC800;&#xC7A5;&#xD560; &#xB0B4;&#xC5ED;&#xC774;
          &#xC5C6;&#xB354;&#xB77C;&#xB3C4; &#xC138;&#xC158;&#xC744; &#xC800;&#xC7A5;&#xD560;&#xC9C0;&#xC5D0;
          &#xB300;&#xD55C; &#xC124;&#xC815;</p>
        <p><b>&#xBCF4;&#xD1B5; &#xBC29;&#xBB38;&#xC790;&#xB97C; &#xCD94;&#xC801;&#xD560; &#xB54C; &#xC0AC;&#xC6A9;</b>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">secret</td>
      <td style="text-align:left">&#xD544;&#xC218; &#xD56D;&#xBAA9;&#xC73C;&#xB85C; cookie-parser&#xC758;
        &#xBE44;&#xBC00;&#xD0A4;&#xC640; &#xAC19;&#xC740; &#xC5ED;&#xD560;</td>
    </tr>
    <tr>
      <td style="text-align:left">httpOnly</td>
      <td style="text-align:left">&#xD074;&#xB77C;&#xC544;&#xC774;&#xB108;&#xD2B8;&#xC5D0;&#xC11C; &#xCFE0;&#xD0A4;&#xB97C;
        &#xD655;&#xC778;&#xD558;&#xC9C0; &#xBABB;&#xD558;&#xB3C4;&#xB85D; &#xD558;&#xB294;
        &#xC5ED;</td>
    </tr>
    <tr>
      <td style="text-align:left">secure</td>
      <td style="text-align:left">https&#xAC00; &#xC544;&#xB2CC; &#xD658;&#xACBD;&#xC5D0;&#xC11C; &#xC0AC;&#xC6A9;&#xD560;
        &#xC218; &#xC788;&#xB294;&#xC9C0; &#xC5EC;&#xBD80;&#xB97C; &#xC815;&#xD558;&#xB294;
        &#xC5ED;&#xD560;</td>
    </tr>
  </tbody>
</table>express-session은 세션 관리 시 클라이언트에 쿠키를 보냅니다. 이를 **세션 쿠키**라 합니다. cookie는 **maxAge**, **domain**, **path**, **expires**, **sameSite**, **httpOnly**, **secure**등 일반적인 쿠키 옵션이 모두 제공됩니다. 

 express-session은 req 객체 안에 **req.session 객체**를 만듭니다. 이 객체에 값을 대입하거나 삭제해서 세션을 변경할 수 있습니다. 

 나중에 **세션을 한번에 삭제하려면 req.session.destroy\(\) 메서드를 호출**하면 되고 **현재 세션의 아이디는 req.sessionID로 확인** 할  수 있습니다.

