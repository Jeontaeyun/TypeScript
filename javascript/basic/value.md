# 자바스크립트의 변수와 자료형

## 자바스크립트의 변수와 자료형

 모든 프로그래밍 언어가 그렇듯 자바스크립트에도 변수와 자료형이 있습니다. 하지만, 자바스크립트에서는 자료형을 명시적으로 지정해주지 않고 할당된 데이터의 값을 분석해 자동으로 자료형을 확하는 **동적 타입 검사**를 수행합니다.

### 자바스크립트의 변수 

```javascript
var people = "hi" ;
const people = "hi";        // ES+
let people = "hi";          // ES+
```

### 자바스크립트의 자료형 

 자바스크립트에서 지원하는 자료의 종류 총7개로 다음과 같습니다.

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>&#xC22B;&#xC790; [Number]</b>
      </td>
      <td style="text-align:left">&#xC22B;&#xC790;&#xB85C; &#xC774;&#xB8E8;&#xC5B4;&#xC9C4; &#xB370;&#xC774;&#xD130;&#xB97C;
        &#xC22B;&#xC790;&#xD615; &#xB370;&#xC774;&#xD130;&#xB77C;&#xACE0; &#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>&#xBB38;&#xC790;&#xC5F4; [String]</b>
      </td>
      <td style="text-align:left">
        <p>&#xBB38;&#xC790;&#xC5F4;&#xC740; &#xD070; &#xB530;&#xC634;&#xD45C;&#xB098;
          &#xC791;&#xC74C; &#xB530;&#xC634;&#xD45C;&#xB85C; &#xC774;&#xB8E8;&#xC5B4;&#xC9C4;
          &#xBB38;&#xC790;&#xC758; &#xB098;&#xC5F4;&#xC744; &#xB9D0;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>&#xBB38;&#xC790;&#xC5F4; &#xC548;&#xC5D0;&#xC11C; &#xC0AC;&#xC6A9;&#xB418;&#xB294;
          \&#xB294; Escaping&#xC774;&#xB77C;&#xACE0; &#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>&#xBD88;&#xB9B0; [Boolean]</b>
      </td>
      <td style="text-align:left">true&#xC640; false&#xC758; &#xAC12;&#xC744; &#xAC19;&#xB294; &#xC790;&#xB8CC;&#xD615;&#xC73C;&#xB85C;
        &#xB17C;&#xB9AC;&#xAC12;&#xC744; &#xB2E4;&#xB8F9;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>&#xAC1D;&#xCCB4; [Object]</b>
      </td>
      <td style="text-align:left">Array, Funciton &#xB4F1;&#xC744; &#xD3EC;&#xD568;&#xD558;&#xB294; &#xC790;&#xB8CC;&#xD615;&#xC785;&#xB2C8;&#xB2E4;.
        &#xD604;&#xC2E4;&#xC758; &#xC0AC;&#xBB3C;&#xC744; &#xD504;&#xB85C;&#xADF8;&#xB798;&#xBC0D;&#xC5D0;
        &#xBC18;&#xC601;&#xD55C; &#xC790;&#xB8CC;&#xD615;&#xC785;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>undefined</b>
      </td>
      <td style="text-align:left">undefined&#xB294; &#xBCC0;&#xC218;&#xB97C; &#xB9CC;&#xB4E4;&#xC5B4; &#xB193;&#xC558;&#xB294;&#xB370;
        &#xC544;&#xBB34; &#xAC12;&#xB3C4; &#xC9D1;&#xC5B4;&#xB123;&#xC9C0; &#xC54A;&#xC558;&#xC744;
        &#xB54C; &#xC790;&#xB3D9;&#xC801;&#xC73C;&#xB85C; &#xC0DD;&#xC131;&#xD558;&#xB294;
        &#xAC12;&#xC785;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>null</b>
      </td>
      <td style="text-align:left">null&#xC740; &#xBE48; &#xAC12;&#xC744; &#xBCC0;&#xC218;&#xC5D0; &#xC758;&#xB3C4;&#xC801;&#xC73C;&#xB85C;
        &#xB123;&#xC740; &#xAC83;&#xC785;&#xB2C8;&#xB2E4;. &#xC8FC;&#xB85C; &#xAE30;&#xC874;&#xC5D0;
        &#xC788;&#xB294; &#xAC12;&#xC744; &#xC9C0;&#xC6B8; &#xB54C; &#xC0AC;&#xC6A9;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Symbol [ES+]</b>
      </td>
      <td style="text-align:left">ES2015+ &#xC5D0; &#xB3C4;&#xC785;&#xB41C; &#xC790;&#xB8CC;&#xD615;&#xC785;&#xB2C8;&#xB2E4;.
        Symbol&#xC740; &#xC6D0;&#xC2DC;&#xAC12;&#xC73C;&#xB85C; &#xC790;&#xAE30;
        &#xC790;&#xC2E0;&#xC744; &#xC81C;&#xC678;&#xD55C; &#xADF8; &#xC5B4;&#xB5A4;
        &#xAC12;&#xACFC;&#xB3C4; &#xAC19;&#xC9C0; &#xC54A;&#xC740; &#xAC12;&#xC785;&#xB2C8;&#xB2E4;.
        Symbol()&#xC744; &#xD1B5;&#xD574;&#xC11C; &#xD638;&#xCD9C;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
  </tbody>
</table>{% hint style="info" %}
자바스크립트를 이해할 때 중요한 것은 function\(함수\)와 array\(배열\)이 모두 객체라는 점입니다. 이 점을 파악하는 것이 자바스크립트를 이해하는데 큰 도움이 됩니다.
{% endhint %}

### Symbol \(ES+\)

 Symbol은 ES2015+부터 추가된 새로운 자료형입니다. 심벌은 자기 자신을 제외한 그 어떤 값과도 다른 유일 무이한 값입니다.

 이는 Symbol\(\)을 사용해서 생성할 수 있습니다. 이는 호출 할 때 마다 새로운 값을 만들며 Symbol\(\)에 인수를 전달하면 생성된 심벌의 설명을 덧붙일 수 있습니다.

```javascript
const Name = Symbol("Stark");
console.log(Name.toString());
// Symbol(stark)
```

