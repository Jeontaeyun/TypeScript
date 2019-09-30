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
      <td style="text-align:left">os.arch()</td>
      <td style="text-align:left">&#xB178;&#xB4DC; &#xC2E4;&#xD589; &#xD658;&#xACBD;&#xC758; &#xD504;&#xB85C;&#xC138;&#xC2A4;
        &#xC544;&#xD0A4;&#xD14D;&#xCCD0;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">os.platform()</td>
      <td style="text-align:left">&#xB178;&#xB4DC; &#xC2E4;&#xD589; &#xD658;&#xACBD;&#xC758; &#xD504;&#xB85C;&#xC138;&#xC2A4;
        &#xC6B4;&#xC601;&#xCCB4;&#xC81C;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">os.type()</td>
      <td style="text-align:left">&#xC6B4;&#xC601; &#xCCB4;&#xC81C;&#xC758; &#xC885;&#xB958;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">os.uptime()</td>
      <td style="text-align:left">
        <p>&#xC6B4;&#xC601;&#xCCB4;&#xC81C; &#xBD80;&#xD305; &#xC774;&#xD6C4; &#xD750;&#xB978;
          &#xC2DC;&#xAC04;(&#xCD08;)&#xC744; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>process.uptime()&#xC740; &#xB178;&#xB4DC; &#xC2E4;&#xD589;&#xC2DC;&#xAC04;
          &#xC785;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">os.hostname()</td>
      <td style="text-align:left">&#xCEF4;&#xD4E8;&#xD130;&#xC758; &#xC774;&#xB984;&#xC744; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">os.release()</td>
      <td style="text-align:left">&#xC6B4;&#xC601;&#xCCB4;&#xC81C;&#xC758; &#xBC84;&#xC804;&#xC744; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">os.homedir()</td>
      <td style="text-align:left">&#xD648; &#xB514;&#xB809;&#xD1A0;&#xB9AC; &#xACBD;&#xB85C;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">os.tmpdir()</td>
      <td style="text-align:left">&#xC784;&#xC2DC; &#xD30C;&#xC77C; &#xC800;&#xC7A5; &#xACBD;&#xB85C;&#xB97C;
        &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">os.cpus()</td>
      <td style="text-align:left">
        <p>&#xCEF4;&#xD4E8;&#xD130;&#xC758; &#xCF54;&#xC5B4; &#xC815;&#xBCF4;&#xB97C;
          &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>- os.cpus().length&#xB97C; &#xD1B5;&#xD574; &#xCF54;&#xC5B4; &#xAC1C;&#xC218;&#xB97C;
          &#xD655;&#xC774;&#xB2C8;&#xD560; &#xC218; &#xC788;&#xC2B5;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">os.freemem()</td>
      <td style="text-align:left">&#xC0AC;&#xC6A9; &#xAC00;&#xB2A5;&#xD55C; &#xBA54;&#xBAA8;&#xB9AC;(RAM)&#xC744;
        &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">os.totalmem()</td>
      <td style="text-align:left">&#xC804;&#xCCB4; &#xBA54;&#xBAA8;&#xB9AC; &#xC6A9;&#xB7C9;&#xC744; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">os.constants</td>
      <td style="text-align:left">&#xAC01; &#xC885; &#xC5D0;&#xB7EC;&#xC640; &#xC2E0;&#xD638;&#xC5D0; &#xB300;&#xD55C;
        &#xC815;&#xBCF4;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
  </tbody>
</table>### path 모듈

 **폴더와 파일의 경로를 쉽게 조작하도록 도와주는 내장 모듈**입니다. 운영 체제 별로 경로 구분자가 다르기 때문에  path 모듈을 사용해 파일명과 확장자만 따로 뗑

### url 모듈 

### querystring 모듈

### crypto 모듈

### util 모듈 

###  

