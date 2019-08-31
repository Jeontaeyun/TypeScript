# 자바스크립트의 내장 타입

## 자바스크립트 내장 타입

 타입스크립트는 자바스크립트에서 지원하는 내장 타입을 제공합니다. 크게 **기본 타입**, **객체 타입**, **함수 타입**이 있습니다.

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xB0B4;&#xC7A5; &#xD0C0;&#xC785;</th>
      <th style="text-align:left">&#xD0C0;&#xC785;&#xC2A4;&#xD06C;&#xB9BD;&#xD2B8; &#xAD6C;&#xBD84;</th>
      <th
      style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>boolean</b>
      </td>
      <td style="text-align:left">&#xB0B4;&#xC7A5; &#xD0C0;&#xC785;</td>
      <td style="text-align:left">&#xB17C;&#xB9AC;&#xC801;&#xC778; &#xAC12;&#xC744; &#xB098;&#xD0C0;&#xB0B4;&#xB294;
        &#xBD88;&#xB9AC;&#xC5B8; &#xD0C0;&#xC785;&#xC73C;&#xB85C; true, false &#xC790;&#xB8CC;&#xD615;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>number</b>
      </td>
      <td style="text-align:left">&#xB0B4;&#xC7A5; &#xD0C0;&#xC785;</td>
      <td style="text-align:left">
        <p>&#xC22B;&#xC790; &#xD0C0;&#xC785;&#xC73C;&#xB85C; &#xC18C;&#xC218;&#xC810;&#xC744;
          &#xAC00;&#xC9C4;&#xB2E4;.</p>
        <p>+Infinity, -Infinity, NaN(Not a Number)&#xD560;&#xB2F9; &#xAC00;&#xB2A5;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>string</b>
      </td>
      <td style="text-align:left">&#xB0B4;&#xC7A5; &#xD0C0;&#xC785;</td>
      <td style="text-align:left">&#xBB38;&#xC790;&#xC5F4; &#xD0C0;&#xC785;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>symbol</b>
      </td>
      <td style="text-align:left">&#xB0B4;&#xC7A5; &#xD0C0;&#xC785;</td>
      <td style="text-align:left">&#xC2EC;&#xBC8C; &#xD568;&#xC218;&#xAC00; &#xBC18;&#xD658;&#xD558;&#xB294;
        &#xAC12;&#xC740; symbol&#xD0C0;&#xC785;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>null</b>
      </td>
      <td style="text-align:left">
        <p>object &#xD0C0;&#xC785;</p>
        <p>(&#xBE48; &#xAC1D;&#xCCB4;&#xC758; &#xD0C0;&#xC785;)</p>
      </td>
      <td style="text-align:left">&#xBE48; &#xAC1D;&#xCCB4;&#xB97C; &#xC758;&#xBBF8;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>undefined</b>
      </td>
      <td style="text-align:left">undefined &#xD0C0;&#xC785;</td>
      <td style="text-align:left">&#xBCC0;&#xC218;&#xB294; &#xC120;&#xC5B8;&#xB410;&#xC9C0;&#xB9CC; &#xAC12;&#xC774;
        &#xD560;&#xB2F9;&#xB418;&#xC9C0; &#xC54A;&#xC74C;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>object</b>
      </td>
      <td style="text-align:left">obejct &#xD0C0;&#xC785;</td>
      <td style="text-align:left">&#xAC1D;&#xCCB4; &#xD0C0;&#xC785;&#xC744; &#xB098;&#xD0C0;&#xB0C4;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>function</b>
      </td>
      <td style="text-align:left">object &#xD558;&#xC704; &#xD0C0;&#xC785;</td>
      <td style="text-align:left">function &#xD0A4;&#xC6CC;&#xB4DC;&#xB85C; &#xC120;&#xC5B8;&#xD55C; &#xD568;&#xC218;&#xC758;
        &#xD0C0;&#xC785;</td>
    </tr>
  </tbody>
</table> 타입스크립트는 지정되니 타입 값만을 할당받도록 **엄격한 타입\(Strong Typed\) 체계**를 사용합니다. 

