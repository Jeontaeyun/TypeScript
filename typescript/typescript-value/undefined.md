# 변수 선언

##  타입스크립트의 변수 선언 

 타입스크립트는 **점진적 타입 검사\(Gradually Type Checking\)**를 수행하는 프로그래밍 언어입니다. 점진적 타입 검사는 컴파일 시간에 타입 검사를 수행하면서 필요에 따라 타입 선언의 생략을 허용합니다. 타입 선언을 생략하면 자동적으로 형변환\(Type Conversion\)이 일어납니다. 

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
        <p>&#xC815;&#xC801; &#xD0C0;&#xC785; &#xAC80;&#xC0AC;</p>
        <p>Statically Type Checking</p>
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
      <td style="text-align:left">&#xB3D9;&#xC801; &#xD0C0;&#xC785; &#xAC80;&#xC0AC; Dynamically Type Checking</td>
      <td
      style="text-align:left">
        <p>&#xD504;&#xB85C;&#xADF8;&#xB7A8;&#xC758; &#xD0C0;&#xC785; &#xAC80;&#xC0AC;&#xB97C;
          &#xC704;&#xD574; &#xC2E4;&#xD589; &#xC2DC;&#xAC04;&#xC5D0; &#xD0C0;&#xC785;
          &#xAC80;&#xC0AC;&#xB97C; &#xC218;&#xD589;&#xD558;&#xB294; &#xD0C0;&#xC785;
          &#xAC80;&#xC0AC; &#xBC29;&#xBC95;</p>
        <p>[&#xC608;&#xC2DC;] JavaScript</p>
        </td>
    </tr>
    <tr>
      <td style="text-align:left">&#xC810;&#xC9C4;&#xC801; &#xD0C0;&#xC785; &#xAC80;&#xC0AC; Gradually Type
        Checking</td>
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

```text
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

| 구분  | 설명  |
| :--- | :--- |
| string |  |
| number |  |
| boolean |  |
| symbol \| ECMA 2015에 추가 |  |
| enum |  |
| 문자열 리터 |  |

#### 객체 타입

| 구분  | 설명  |
| :--- | :--- |
| Array |  |
| Tuple |  |
| Function |  |
| 생성자 |  |
| Class |  |
| Interface |  |

#### 기타 타입

| 구분  | 설명  |
| :--- | :--- |
| 유니언\(Union\) |  |
| 인터섹션\(Intersection\) |  |
| 특수 타입  |  |



