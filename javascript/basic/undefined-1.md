# 자바스크립트의 정규 표현식

## 정규 표현식  Regular Expressions

 정규식은 문자열에 포함된 문자 조합을 찾기 위해 사용되는 패턴입니다. 코드를 간략하게 만들 수 있으나, 가독성이 떨어질 수 있습니다. 

### 정규 표현식 메소드 

 정규 표현식은 RegExp의 exec메소드와 test메소드로 사용할 수 있습니다. 

#### 정규 표현식 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">exec</td>
      <td style="text-align:left">
        <p>&#xB9E4;&#xCE6D;&#xB41C; &#xBB38;&#xC790;&#xC5F4;&#xC744; &#xCC3E;&#xAE30;
          &#xC704;&#xD55C; &#xBA54;&#xC18C;&#xB4DC;&#xC785;&#xB2C8;&#xB2E4;.</p>
        <p>&#xB9E4;&#xCE6D;&#xB41C; &#xBB38;&#xC790;&#xC5F4;&#xC774; &#xC788;&#xB2E4;&#xBA74;
          &#xB9E4;&#xCE6D;&#xB41C; &#xAC12;&#xC758; &#xBC30;&#xC5F4;&#xC744; &#xB9AC;&#xD134;&#xD558;&#xACE0;,
          &#xB9E4;&#xCE6D;&#xB41C; &#xBB38;&#xC790;&#xC5F4;&#xC774; &#xC5C6;&#xB2E4;&#xBA74;
          null&#xC744; &#xB9AC;&#xD134;&#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">test</td>
      <td style="text-align:left">
        <p>&#xB9E4;&#xCE6D;&#xB41C; &#xBB38;&#xC790;&#xC5F4;&#xC774; &#xC788;&#xB294;&#xC9C0;
          &#xD655;&#xC778;&#xD558;&#xAE30; &#xC704;&#xD55C; &#xBA54;&#xC18C;&#xB4DC;&#xC785;&#xB2C8;&#xB2E4;.</p>
        <p>&#xB9E4;&#xCE6D;&#xB41C; &#xBB38;&#xC790;&#xC5F4;&#xC774; &#xC788;&#xB2E4;&#xBA74;
          true&#xB97C; &#xB9AC;&#xD134;&#xD558;&#xACE0;, &#xB9E4;&#xCE6D;&#xB41C;
          &#xBB38;&#xC790;&#xC5F4;&#xC774; &#xC5C6;&#xB2E4;&#xBA74; false&#xB97C;
          &#xB9AC;&#xD134;&#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
  </tbody>
</table>```javascript
const myRe = /d(b+)d/g; 또는 const myRe = RegExp('d(b+)d', 'g');
const myArray = myRe.exec('cdbbdbsbz');
```

#### String 메소드

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">match(&#xC815;&#xADDC;&#xC2DD;)</td>
      <td style="text-align:left">
        <p>&#xB9E4;&#xCE6D;&#xB41C; &#xBB38;&#xC790;&#xC5F4;&#xC744; &#xCC3E;&#xAE30;
          &#xC704;&#xD55C; &#xBA54;&#xC18C;&#xB4DC;</p>
        <p>&#xB9E4;&#xCE6D;&#xB41C; &#xBB38;&#xC790;&#xC5F4;&#xC774; &#xC788;&#xB2E4;&#xBA74;
          &#xB9E4;&#xCE6D;&#xB41C; &#xAC12;&#xC758; &#xBC30;&#xC5F4;&#xC744; &#xBC18;&#xD658;&#xD558;&#xACE0;,
          &#xB9E4;&#xCE6D;&#xB41C; &#xBB38;&#xC790;&#xC5F4;&#xC774; &#xC5C6;&#xC73C;&#xBA74;
          null&#xC744; &#xBC18;&#xD658;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">search(&#xC815;&#xADDC;&#xC2DD;)</td>
      <td style="text-align:left">
        <p>&#xB9E4;&#xCE6D;&#xB41C; &#xBB38;&#xC790;&#xC5F4;&#xC774; &#xC788;&#xB294;&#xC9C0;
          &#xD655;&#xC778;&#xD558;&#xAE30; &#xC704;&#xD55C; &#xBA54;&#xC18C;&#xB4DC;</p>
        <p>&#xB9E4;&#xCE6D;&#xB41C; &#xBB38;&#xC790;&#xC5F4;&#xC774; &#xC788;&#xB2E4;&#xBA74;
          &#xB9E4;&#xCE6D;&#xB41C; &#xBB38;&#xC790;&#xC5F4;&#xC758; &#xC778;&#xB371;&#xC2A4;&#xB97C;
          &#xB9AC;&#xD134;&#xD558;&#xACE0;, &#xB9E4;&#xCE6D;&#xB41C; &#xBB38;&#xC790;&#xC5F4;&#xC774;
          &#xC5C6;&#xB2E4;&#xBA74; null&#xC744; &#xBC18;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">replace(&#xC815;&#xADDC;&#xC2DD;)</td>
      <td style="text-align:left">&#xB9E4;&#xCE6D;&#xB41C; &#xBB38;&#xC790;&#xC5F4;&#xC744; &#xCC3E;&#xC544;
        &#xB9E4;&#xCE6D;&#xB41C; &#xBB38;&#xC790;&#xC5F4;&#xC744; &#xBCC0;&#xACBD;&#xD558;&#xB294;
        &#xBA54;&#xC18C;&#xB4DC;</td>
    </tr>
    <tr>
      <td style="text-align:left">split(&#xC815;&#xADDC;&#xC2DD;)</td>
      <td style="text-align:left">&#xB9E4;&#xCE6D;&#xB41C; &#xBB38;&#xC790;&#xC5F4;&#xC744; &#xCC3E;&#xC544;
        &#xADF8; &#xBB38;&#xC790;&#xC5F4;&#xC744; &#xAE30;&#xC900;&#xC73C;&#xB85C;
        &#xBB38;&#xC790;&#xC5F4;&#xC744; &#xB098;&#xB204;&#xB294; &#xBA54;&#xC18C;&#xB4DC;</td>
    </tr>
  </tbody>
</table>### 정규식 만들기 

 정규식은 다음 두 가지 방법으로 만들 수 있습니다. 

```javascript
// 정규식 패턴이 계속 지속될 경우
const re = /ab+c/;
// 정규식 패턴이 변경되는 경우
const re = new RegExp("ab+c");
```

### 정규식 패턴 만들기 

 정규식 패턴 /abc/와 같이 단순한 문자열로 만들 수도 있고 /ab\*c/또는 /\(\d+\)\.=d%/와 같이 **특수 문자열과 단순 문자열의 조합**으로 만들 수 있습니다.

### 정규식 특수 문자 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">\</td>
      <td style="text-align:left">
        <p>01. &#xB2E8;&#xC21C; &#xBB38;&#xC790; &#xC55E;&#xC758; \&#xB294; &#xB2E8;&#xC21C;
          &#xBB38;&#xC790;&#xB85C; &#xD574;&#xC11D;&#xB418;&#xC9C0; &#xC54A;&#xACE0;
          &#xB2E4;&#xB978; &#xC758;&#xBBF8;&#xB85C; &#xD574;&#xC11C;&#xB429;&#xB2C8;&#xB2E4;.</p>
        <p>02. &#xD2B9;&#xC218; &#xBB38;&#xC790; &#xC55E;&#xC758; \&#xB294; &#xD2B9;&#xC218;
          &#xBB38;&#xC790;&#xB97C; &#xB2E8;&#xC21C; &#xBB38;&#xC790;&#xB85C; &#xD574;&#xC11D;&#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">^</td>
      <td style="text-align:left">&#xC785;&#xB825;&#xC758; &#xC2DC;&#xC791; &#xBB38;&#xC790;&#xC5F4;&#xC5D0;
        &#xB9E4;&#xCE6D;&#xB429;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">$</td>
      <td style="text-align:left">&#xC785;&#xB825;&#xC758; &#xB05D; &#xBB38;&#xC790;&#xC5F4;&#xC5D0; &#xB9E4;&#xCE6D;&#xB429;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">*</td>
      <td style="text-align:left">
        <p><b>0&#xBC88; &#xC774;&#xC0C1; &#xBC18;&#xBCF5;</b>&#xB418;&#xB294; &#xBB38;&#xC790;&#xC5F4;&#xC5D0;
          &#xB9E4;&#xCE6D;&#xB429;&#xB2C8;&#xB2E4;. {0,}&#xACFC; &#xB3D9;&#xC77C;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>0&#xBC88; &#xC774;&#xC0C1;&#xC740; 0&#xBC88;&#xB3C4; &#xD3EC;&#xD568;&#xB418;&#xB294;
          &#xAC83; &#xC774;&#xB77C;&#xB294; &#xC810;&#xC744; &#xBA85;&#xC2EC;&#xD574;&#xC57C;
          &#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">+</td>
      <td style="text-align:left"><b>1&#xBC88; &#xC774;&#xC0C1; &#xBC18;&#xBCF5;</b>&#xB418;&#xB294; &#xBB38;&#xC790;&#xC5F4;&#xC5D0;
        &#xB9E4;&#xCE6D;&#xB429;&#xB2C8;&#xB2E4;. {1,}&#xACFC; &#xB3D9;&#xC77C;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">?</td>
      <td style="text-align:left">
        <p>0~1&#xBC88; &#xBC18;&#xBCF5;&#xB418;&#xB294; &#xBB38;&#xC790;&#xC5F4;&#xC5D0;
          &#xB9E4;&#xCE6D;&#xB429;&#xB2C8;&#xB2E4;. {0,1}&#xACFC; &#xB3D9;&#xC77C;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>*, +, ?, {} &#xD328;&#xD134;&#xC740; &#xAC00;&#xB2A5; &#xD55C; &#xB9CE;&#xC740;
          &#xBB38;&#xC790;&#xC5F4;&#xC744; &#xB9E4;&#xCE6D;&#xC2DC;&#xD0A4;&#xB294;&#xB370;,
          &#xC774; &#xB4A4;&#xC5D0; ?&#xAC00; &#xBD99;&#xC73C;&#xBA74; &#xAC00;&#xB2A5;&#xD55C;
          &#xAC00;&#xC7A5; &#xC801;&#xC740; &#xBB38;&#xC790;&#xC5F4;&#xC744; &#xB9E4;&#xCE6D;&#xC2DC;&#xD0B5;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">.</td>
      <td style="text-align:left">&#xB2E4;&#xC74C; &#xC904; &#xBB38;&#xC790;(&#xAC1C;&#xD589; &#xBB38;&#xC790;)&#xB97C;
        &#xC81C;&#xC678;&#xD55C; &#xBB38;&#xC790;&#xC5F4;&#xC5D0; &#xB9E4;&#xCE6D;&#xB429;&#xB2C8;&#xB2E4;.</td>
    </tr>
  </tbody>
</table>