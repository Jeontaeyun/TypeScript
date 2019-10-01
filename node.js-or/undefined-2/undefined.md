# 노드 내장 모듈

## 노드 내장 모듈 Built-in Module

 노드는 운영체제 정보에도 접근할 수 있고, 클라이언트가 요청한 주소에 대한 정보도 가져올 수 있는 등 다양한 기능을 제공합니다. 대표적으로 자주  사용하는 노드 모듈에 대해 알아봅시다. 

###  OS 모듈

 **운영체제에 대한 정보를 반환하는 내장 모듈**입니다. 다음과 같이 사용할 수 있습니다 .

```javascript
const os = require("os");

console.log("os.type() : ", os.type());
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>os.arch()</b>
      </td>
      <td style="text-align:left">&#xB178;&#xB4DC; &#xC2E4;&#xD589; &#xD658;&#xACBD;&#xC758; &#xD504;&#xB85C;&#xC138;&#xC2A4;
        &#xC544;&#xD0A4;&#xD14D;&#xCCD0;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>os.platform() </b>
      </td>
      <td style="text-align:left">&#xB178;&#xB4DC; &#xC2E4;&#xD589; &#xD658;&#xACBD;&#xC758; &#xD504;&#xB85C;&#xC138;&#xC2A4;
        &#xC6B4;&#xC601;&#xCCB4;&#xC81C;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>os.type() </b>
      </td>
      <td style="text-align:left">&#xC6B4;&#xC601; &#xCCB4;&#xC81C;&#xC758; &#xC885;&#xB958;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>os.uptime()</b>
      </td>
      <td style="text-align:left">
        <p>&#xC6B4;&#xC601;&#xCCB4;&#xC81C; &#xBD80;&#xD305; &#xC774;&#xD6C4; &#xD750;&#xB978;
          &#xC2DC;&#xAC04;(&#xCD08;)&#xC744; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>process.uptime()&#xC740; &#xB178;&#xB4DC; &#xC2E4;&#xD589;&#xC2DC;&#xAC04;
          &#xC785;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>os.hostname()</b>
      </td>
      <td style="text-align:left">&#xCEF4;&#xD4E8;&#xD130;&#xC758; &#xC774;&#xB984;&#xC744; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>os.release() </b>
      </td>
      <td style="text-align:left">&#xC6B4;&#xC601;&#xCCB4;&#xC81C;&#xC758; &#xBC84;&#xC804;&#xC744; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>os.homedir()</b>
      </td>
      <td style="text-align:left">&#xD648; &#xB514;&#xB809;&#xD1A0;&#xB9AC; &#xACBD;&#xB85C;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>os.tmpdir()</b>
      </td>
      <td style="text-align:left">&#xC784;&#xC2DC; &#xD30C;&#xC77C; &#xC800;&#xC7A5; &#xACBD;&#xB85C;&#xB97C;
        &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>os.cpus()</b>
      </td>
      <td style="text-align:left">
        <p>&#xCEF4;&#xD4E8;&#xD130;&#xC758; &#xCF54;&#xC5B4; &#xC815;&#xBCF4;&#xB97C;
          &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>- os.cpus().length&#xB97C; &#xD1B5;&#xD574; &#xCF54;&#xC5B4; &#xAC1C;&#xC218;&#xB97C;
          &#xD655;&#xC774;&#xB2C8;&#xD560; &#xC218; &#xC788;&#xC2B5;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>os.freemem()</b>
      </td>
      <td style="text-align:left">&#xC0AC;&#xC6A9; &#xAC00;&#xB2A5;&#xD55C; &#xBA54;&#xBAA8;&#xB9AC;(RAM)&#xC744;
        &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>os.totalmem()</b>
      </td>
      <td style="text-align:left">&#xC804;&#xCCB4; &#xBA54;&#xBAA8;&#xB9AC; &#xC6A9;&#xB7C9;&#xC744; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>os.constants</b>
      </td>
      <td style="text-align:left">&#xAC01; &#xC885; &#xC5D0;&#xB7EC;&#xC640; &#xC2E0;&#xD638;&#xC5D0; &#xB300;&#xD55C;
        &#xC815;&#xBCF4;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
  </tbody>
</table>### path 모듈

 **폴더와 파일의 경로를 쉽게 조작하도록 도와주는 내장 모듈**입니다. 운영 체제 별로 경로 구분자가 다르기 때문에  path 모듈을 사용해 파일명과 확장자만 따로 떼어주는 등을 쉽게 구현할 수 있습니다. 

{% hint style="info" %}
**window는 \\(역슬래쉬\)**로 경로를 구분하고  
**유닉스 기반\(POSIX\)은 /\(슬래쉬\)**로 경로를 구분합니다. 
{% endhint %}

 path 모듈의 기능은 다음과 같습니다. 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>path.sep</b>
      </td>
      <td style="text-align:left">&#xACBD;&#xB85C;&#xC758; &#xAD6C;&#xBD84;&#xC790;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>path.delimiter</b>
      </td>
      <td style="text-align:left">
        <p>&#xD658;&#xACBD; &#xBCC0;&#xC218;&#xC758; &#xAD6C;&#xBD84;&#xC790;&#xB97C;
          &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>process.env.PATH&#xB97C; &#xC785;&#xB824;&#xD558;&#xBA74; &#xC5EC;&#xB7EC;
          &#xAC1C;&#xC758; &#xACBD;&#xB85C;&#xAC00; &#xC774; &#xAD6C;&#xBD84;&#xC790;&#xB85C;
          &#xAD6C;&#xBD84;&#xB418;&#xC5B4; &#xC788;&#xC2B5;&#xB2C8;&#xB2E4;.</p>
        <p>Window&#xB294; &#xC138;&#xBBF8;&#xCF5C;&#xB860;(;)&#xC774;&#xACE0; POSIX&#xB294;
          &#xCF5C;&#xB860;(:)&#xC744; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>path.dirname(&#xACBD;&#xB85C;)</b>
      </td>
      <td style="text-align:left">&#xD30C;&#xC77C;&#xC774; &#xC704;&#xCE58;&#xD55C; &#xD3F4;&#xB354;&#xC758;
        &#xACBD;&#xB85C;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>path.extname(&#xACBD;&#xB85C;)</b>
      </td>
      <td style="text-align:left">&#xD30C;&#xC77C;&#xC758; &#xD655;&#xC7A5;&#xC790;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>path.basename(&#xACBD;&#xB85C;, &#xD655;&#xC7A5;&#xC790;) </b>
      </td>
      <td style="text-align:left">
        <p>&#xD30C;&#xC77C;&#xC758; &#xC774;&#xB984;(&#xD655;&#xC7A5;&#xC790; &#xD3EC;&#xD568;)&#xC744;
          &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>&#xD30C;&#xC77C; &#xC774;&#xB984;&#xB9CC; &#xBC18;&#xD658;&#xD558;&#xACE0;
          &#xC2F6;&#xC744; &#xB54C; &#xB450; &#xBC88;&#xC9F8; &#xC778;&#xC790;&#xB85C;
          &#xD655;&#xC7A5;&#xC790;&#xB97C; &#xB123;&#xC5B4;&#xC90D;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>path.parse(&#xACBD;&#xB85C;) </b>
      </td>
      <td style="text-align:left">&#xD30C;&#xC77C;&#xC758; &#xACBD;&#xB85C;&#xB97C; root, dir, base, ext,
        name&#xC73C;&#xB85C; &#xAD6C;&#xBD84;&#xD558;&#xC5EC; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>path.format(&#xAC1D;&#xCCB4;) </b>
      </td>
      <td style="text-align:left">path.parse()&#xD55C; &#xAC1D;&#xCCB4;&#xB97C; &#xD30C;&#xC77C; &#xACBD;&#xB85C;&#xB85C;
        &#xD569;&#xCCD0; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>path.normalize(&#xACBD;&#xB85C;) </b>
      </td>
      <td style="text-align:left">/&#xB098; \&#xB97C; &#xC2E4;&#xC218;&#xB85C; &#xC5EC;&#xB7EC; &#xBC88;
        &#xC0AC;&#xC6A9;&#xD588;&#xC744; &#xB54C; &#xC815;&#xC0C1;&#xC801;&#xC778;
        &#xACBD;&#xB85C;&#xB85C; &#xBCC0;&#xD658; &#xD6C4; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>path.isAbsolute(&#xACBD;&#xB85C;) </b>
      </td>
      <td style="text-align:left">&#xD30C;&#xC77C;&#xC758; &#xACBD;&#xB85C;&#xAC00; &#xC808;&#xB300; &#xACBD;&#xB85C;&#xC778;&#xC9C0;
        &#xC0C1;&#xB300;&#xACBD;&#xB85C;&#xC778;&#xC9C0; true&#xB098; false&#xB85C;
        &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>path.relative(&#xAE30;&#xC900;&#xACBD;&#xB85C;, &#xBE44;&#xAD50;&#xACBD;&#xB85C;) </b>
      </td>
      <td style="text-align:left">&#xACBD;&#xB85C;&#xB97C; &#xB450; &#xAC1C; &#xB123;&#xC73C;&#xBA74; &#xAE30;&#xC900;
        &#xACBD;&#xB85C;&#xC5D0;&#xC11C; &#xBE44;&#xAD50; &#xACBD;&#xB85C;&#xB85C;
        &#xAC00;&#xB294; &#xAC00;&#xB294; &#xBC29;&#xBC95;&#xC744; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>path.join(&#xACBD;&#xB85C;, ...) </b>
      </td>
      <td style="text-align:left">&#xC5EC;&#xB7EC; &#xC778;&#xC790;&#xB97C; &#xB123;&#xC73C;&#xBA74; &#xD558;&#xB098;&#xC758;
        &#xACBD;&#xB85C;&#xB85C; &#xD569;&#xCCD0;&#xC90D;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>path.resolve(&#xACBD;&#xB85C;, ...) </b>
      </td>
      <td style="text-align:left">path.join()&#xACFC; &#xBE44;&#xC2B7;&#xD55C; &#xACBD;&#xC6B0;.</td>
    </tr>
  </tbody>
</table>### url 모듈 

url은 인터넷 주소를 쉽게 조작하도록 도와주는 모듈입니다.  

### querystring 모듈

 url을 분석할 때 search 부분을 사용하기 쉽게 객체로 만드는 모듈입니다. 

| 구분  | 설명  |
| :--- | :--- |
| **querystring.parse\(쿼리\)**  | url의 query 부분을 자바스크립트 객체로 분해해줍니다.  |
| **querystring.stringify\(객체\)** | 분해된 query 객체를 문자열로 다시 조립해줍니다.  |

### crypto 모듈

 다양한 방식의 암호화를 도와주는 모듈입니다. 

### util 모듈 

###  

