# 변수 선언

##  타입스크립트의 변수 선언 

 타입스크립트는 **점진적 타입 검사\(Gradually Type Checking\)**를 수행하는 프로그래밍 언어입니다. 점진적 타입 검사는 컴파일 시간에 타입 검사를 수행하면서 필요에 따라 타입 선언의 생략을 허용합니다. 타입 선언을 생략하면 자동적으로 **형변환\(Type Conversion\)**이 일어납니다. 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>&#xC815;&#xC801; &#xD0C0;&#xC785; &#xAC80;&#xC0AC;</b>
        </p>
        <p><b>Statically Type Checking</b>
        </p>
      </td>
      <td style="text-align:left">
        <p>&#xD504;&#xB85C;&#xADF8;&#xB7A8;&#xC758; &#xD0C0;&#xC785;&#xC744; &#xAC80;&#xC0AC;&#xD558;&#xAE30;
          &#xC704;&#xD574; &#xB2E4;&#xB978; &#xD30C;&#xC77C; &#xC2DC;&#xAC04;&#xC5D0;
          &#xD0C0;&#xC785; &#xAC80;&#xC0AC;&#xB97C; &#xC218;&#xD589;&#xD558;&#xB294;
          &#xD0C0;&#xC785; &#xAC80;&#xC0AC; &#xBC29;&#xBC95;</p>
        <p>[&#xC608;&#xC2DC;] C++, java</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>&#xB3D9;&#xC801; &#xD0C0;&#xC785; &#xAC80;&#xC0AC; Dynamically Type Checking</b>
      </td>
      <td style="text-align:left">
        <p>&#xD504;&#xB85C;&#xADF8;&#xB7A8;&#xC758; &#xD0C0;&#xC785; &#xAC80;&#xC0AC;&#xB97C;
          &#xC704;&#xD574; &#xC2E4;&#xD589; &#xC2DC;&#xAC04;&#xC5D0; &#xD0C0;&#xC785;
          &#xAC80;&#xC0AC;&#xB97C; &#xC218;&#xD589;&#xD558;&#xB294; &#xD0C0;&#xC785;
          &#xAC80;&#xC0AC; &#xBC29;&#xBC95;</p>
        <p>[&#xC608;&#xC2DC;] JavaScript</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>&#xC810;&#xC9C4;&#xC801; &#xD0C0;&#xC785; &#xAC80;&#xC0AC; Gradually Type Checking</b>
      </td>
      <td style="text-align:left">
        <p>&#xC815;&#xC801; &#xD0C0;&#xC785; &#xAC80;&#xC0AC;&#xC640; &#xAC19;&#xC774;
          &#xCEF4;&#xD30C;&#xC77C; &#xC2DC;&#xAC04;&#xC5D0; &#xD0C0;&#xC785; &#xAC80;&#xC0AC;&#xB97C;
          &#xC218;&#xD589;&#xD558;&#xBA74;&#xC11C; &#xD544;&#xC694;&#xC5D0; &#xB530;&#xB77C;
          &#xD0C0;&#xC785; &#xC120;&#xC5B8;&#xC744; &#xC0DD;&#xB7B5;&#xD558;&#xAC70;&#xB098;
          &#xC810;&#xC9C4;&#xC801;&#xC73C;&#xB85C; &#xD0C0;&#xC785;&#xC744; &#xCD94;&#xAC00;&#xD560;
          &#xC218; &#xC788;&#xB294; &#xD0C0;&#xC785; &#xAC80;&#xC0AC; &#xBC29;&#xBC95;</p>
        <p>[&#xC608;&#xC2DC;] TypeScript, Python</p>
      </td>
    </tr>
  </tbody>
</table>### 자바스크립트의 동적 타이핑 \| Dynamic Typing

 자바스크립트에는 타입이 있지만, 타입을 강제할 수 없고 값을 할당할 때 타입이 추론됩니다. 이처럼 값을 변수에 할당할 때 타입이 정해지는 것을 **동적 타이핑\(Dynamic Typing\)**이라 합니다.

 타입스크립트에서는 타입을 선언하지 않으면 입력값에 따라 타입이 결정됩니다.

```javascript
const value = 100;                 // Number 타입
const value = "This is Typescript" // String 타입
const value = false;               // Boolean 타입
```

### 타입 계층도

 점진적 타입 시스템을 더욱 잘 이해하려면 타입 시스템의 계층 구조를 알아둘 필요가 있습니다. 타입 계층도에서 모든 타입을 받을 수 있는 any 타입이 가장 상위에 있고 그 아래로 다음과 같은 타입이 있습니다.

* 기본 타입
* 객체 타입
* 기타 타입\(유니언 타입, 인터섹션 타입\)

#### 기본 타입 \| Primitive Types

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>string</b>
      </td>
      <td style="text-align:left">&#xBB38;&#xC790;&#xC5F4; &#xD0C0;&#xC785;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>number</b>
      </td>
      <td style="text-align:left">
        <p>&#xC22B;&#xC790; &#xD0C0;&#xC785;</p>
        <p>10&#xC9C4;&#xC218; &#xBFD0;&#xB9CC; &#xC544;&#xB2C8;&#xB77C; 16&#xC9C4;&#xC218;,
          2&#xC9C4;&#xC218;, 8&#xC9C4;&#xC218; &#xC9C0;&#xC6D0;&#xD55C;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>boolean</b>
      </td>
      <td style="text-align:left">&#xBD88;&#xB9AC;&#xC5B8; &#xD0C0;&#xC785;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>symbol</b>
      </td>
      <td style="text-align:left">
        <p>Symbol()&#xD568;&#xC218;&#xB97C; &#xC774;&#xC6A9;&#xD574; &#xC0DD;&#xC131;&#xD55C;
          &#xACE0;&#xC720;&#xD558;&#xACE0; &#xC218;&#xC815; &#xBD88;&#xAC00;&#xB2A5;&#xD55C;
          &#xB370;&#xC774;&#xD130; &#xD0C0;&#xC785;&#xC73C;&#xB85C; ECMA 2015&#xBD80;&#xD130;
          &#xCD94;&#xAC00;&#xB428;.</p>
        <p>&#xAC1D;&#xCCB4; &#xC18D;&#xC131;&#xC758; &#xC2DD;&#xBCC4;&#xC790;&#xB85C;
          &#xC0AC;&#xC6A9;&#xB429;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>enum</b>
      </td>
      <td style="text-align:left">number&#xC5D0;&#xC11C; &#xD655;&#xC7A5;&#xB41C; &#xD0C0;&#xC785;&#xC73C;&#xB85C;
        &#xCCAB; &#xBC88;&#xC9F8; Enum &#xC694;&#xC18C;&#xC5D0;&#xB294; &#xC22B;&#xC790;
        0 &#xAC12;&#xC774; &#xD560;&#xB2F9;&#xB429;&#xB2C8;&#xB2E4;. &#xADF8;&#xB2E4;&#xC74C;
        &#xAC12;&#xC740; &#xD2B9;&#xBCC4;&#xD788; &#xCD08;&#xAE30;&#xD654;&#xD558;&#xC9C0;
        &#xC54A;&#xB294; &#xC774;&#xC0C1; 1&#xC529; &#xC99D;&#xAC00;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>&#xBB38;&#xC790;&#xC5F4; &#xB9AC;&#xD130;</b>
      </td>
      <td style="text-align:left">
        <p>string &#xD0C0;&#xC785;&#xC758; &#xD655;&#xC7A5; &#xD0C0;&#xC785;&#xC73C;&#xB85C;
          &#xC0AC;&#xC6A9;&#xC790; &#xC815;&#xC758; &#xD0C0;&#xC785;&#xC5D0; &#xC815;&#xC758;&#xD55C;
          &#xBB38;&#xC790;&#xC5F4;&#xB9CC; &#xD560;&#xB2F9; &#xBC1B;&#xC744; &#xC218;
          &#xC788;&#xC2B5;&#xB2C8;&#xB2E4;.</p>
        <p>type &lt;&#xBB38;&#xC790;&#xC5F4;&#xB9AC;&#xD130;&#xB7F4;&#xC774;&#xB984;&gt;
          = &quot;keyup&quot; | &quot;mouseover&quot; ;</p>
      </td>
    </tr>
  </tbody>
</table>#### 객체 타입 \| Object Types

 객체 타입은 속성을 포함하고 있으며, **호출 시그니처\(Call signature\)**, **생성자 시그니처\(Construct signature\)**등으로 구성된 타입입니다.

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Array</td>
      <td style="text-align:left">&#xBC30;&#xC5F4; &#xC694;&#xC18C;&#xC5D0; &#xB300;&#xC751;&#xD558;&#xB294;
        &#xD0C0;&#xC785;</td>
    </tr>
    <tr>
      <td style="text-align:left">Tuple</td>
      <td style="text-align:left">&#xBC30;&#xC5F4; &#xC694;&#xC18C;&#xAC00; n&#xAC1C;&#xB85C; &#xC815;&#xD574;&#xC9C8;
        &#xB54C; &#xAC01; &#xC694;&#xC18C;&#xBCC4;&#xB85C; &#xD0C0;&#xC785;&#xC744;
        &#xC9C0;&#xC815;&#xD55C; &#xD0C0;&#xC785;</td>
    </tr>
    <tr>
      <td style="text-align:left">Function</td>
      <td style="text-align:left">&#xD568;&#xC218; &#xD0C0;&#xC785;&#xC740; &#xD638;&#xCD9C; &#xC2DC;&#xADF8;&#xB2C8;&#xCC98;&#xB97C;
        &#xD3EC;&#xD568;&#xD558;&#xB3C4;&#xB85D; &#xC815;&#xC758;&#xD55C; &#xD0C0;&#xC785;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xC0DD;&#xC131;&#xC790;</td>
      <td style="text-align:left">
        <p>&#xD558;&#xB098;&#xC758; &#xAC1D;&#xCCB4;(&#xD074;&#xB798;&#xC2A4;&#xB85C;&#xBD80;&#xD130;
          &#xC0DD;&#xC131;)&#xAC00; &#xC5EC;&#xB7EC; &#xC0DD;&#xC131;&#xC790;&#xC758;
          &#xC2DC;&#xADF8;&#xB2C8;&#xCC98;&#xB85C; &#xAD6C;&#xC131;&#xB420; &#xB54C;
          &#xD3EC;&#xD568;&#xD560; &#xC218; &#xC788;&#xB294; &#xD0C0;&#xC785;</p>
        <p>&#xC0DD;&#xC131;&#xC790; &#xD0C0;&#xC785; &#xB9AC;&#xD130;&#xB7F4;(Constructor
          Type Literal)&#xC744; &#xC0AC;&#xC6A9;&#xD574; &#xC815;&#xC758;&#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Class</td>
      <td style="text-align:left">&#xAC1D;&#xCCB4; &#xD0C0;&#xC785;</td>
    </tr>
    <tr>
      <td style="text-align:left">Interface</td>
      <td style="text-align:left">&#xAC1D;&#xCCB4; &#xD0C0;&#xC785;</td>
    </tr>
  </tbody>
</table>#### 기타 타입

| 구분  | 설명  |
| :--- | :--- |
| 유니언\(Union\) | 2개 이상의 타입을 하나의 타입으로 정의한 타입  |
| 인터섹션\(Intersection\) | 두 타입을 합쳐 하나로 만들 수 있는 타입 |
| 특수 타입  | void, undefined, null 과 같은 타입  |

### 변수의 타입 지정

 타입스크립트는 강력한 타입을 지원합니다. 변수에 타입을 지정하려면 다음과 같은 형식으로 선언합니다.

```javascript
const <변수 식별자> : <타입> = <값>;
```

 **명시적 타입 표기\(Explicit Type Annotation\)**를 하면 변수에 어떤 값이 할당될 지 직관적으로 알 수 있습니다. 만약 타입이 일치하지 않는다면 코드 어시스트가 동작해 타입이 일치하지 않는다는 오류를 표시하고, 컴파일할 때도 오류가 발생합니다. 

