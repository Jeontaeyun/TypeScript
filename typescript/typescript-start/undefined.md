---
description: '타입스크립트는 마이크로 소프트에서 개발하고 관리하는 오픈 소스 프로그래밍 언어입니다. 모든 브라우저나 호스트, 운영체제에서도 동작합니다.'
---

# 타입스크립트?

## 타입스크립트란 무엇인가? \| What is TypeScript

 타입스크립트\(TypeScript\)는 마이크로 소프트웨어에서 개발했고 유지관리하는 오픈 소스 프로그래밍 언어입니다. 자바스크립트가 웹 브라우저를 제어하는 언어를 넘어 하나의 프로그래밍 언어인 NODE.js가 되면서 자바스크립트를 이용한 다양한 프로그램이 개발되고 있습니다. 

 하지만 자바스크립트를 대규모 어플리케이션을 개발하는데 타입을 지원하지 않고 생산성이 떨어진다는 단점이 있습니다. 고객사들의 대규모 어플리케이션 개발의 어려움에 마이크로 소프트웨어에서는 자바스크립트의 단점을 보완한 타입스크립트를 만들었습니다.

 즉, 타입스크립트는 자바스크립트의 결함을 보완해 대규모 어플리케이션을 만드는 데 유용한 오픈 소스 프로그래밍 언어입니다. 

### ECMA Script의 역사

 유럽 컴퓨터 제조사 연합\(European Computer Manufactures Association\)의 약자인 ECMA는 스크립트의 표즌을 만들고 관리하는 단체입니다. 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">ES6 | ES2015</td>
      <td style="text-align:left">
        <ul>
          <li>&#xBAA8;&#xB4C8;&#xC2DC;&#xC2A4;&#xD15C; | Module</li>
          <li>&#xD654;&#xC0B4;&#xD45C; &#xD568;&#xC218; | Arrow Function</li>
          <li>&#xD074;&#xB798;&#xC2A4;</li>
          <li>&#xAC1C;&#xC120;&#xB41C; &#xAC1D;&#xCCB4; &#xB9AC;&#xD130;</li>
          <li>&#xD15C;&#xD50C;&#xB9BF; &#xBB38;&#xC790;&#xC5F4;</li>
          <li>&#xC2EC;&#xBCFC;(Symbol)</li>
          <li>&#xD504;&#xB85C;&#xBBF8;&#xC2A4;(Promise)</li>
          <li>&#xC81C;&#xB108;&#xB808;&#xC774;&#xD130;&#xC640; yield</li>
          <li>&#xAD6C;&#xC870; &#xBD84;&#xD574; &#xD560;&#xB2F9; | Destructuring Assignment</li>
          <li>for of</li>
          <li>&#xD504;&#xC2DC;(Proxy)</li>
          <li>&#xC720;&#xB2C8;&#xCF54;&#xB4DC;</li>
          <li>let, const</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">ES 7 | ES 2016</td>
      <td style="text-align:left">
        <ul>
          <li>Async/ Await | &#xBE44;&#xB3D9;&#xAE30;&#xD568;&#xC218;&#xB97C; &#xB3D9;&#xAE30;&#xD654;
            &#xD558;&#xB294; &#xBB38;&#xBC95;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">ES 8 | ES 2017</td>
      <td style="text-align:left">
        <ul>
          <li>&#xBB38;&#xC790;&#xC5F4; &#xD328;&#xB529; | String Padding</li>
          <li>Object.values &#xBA54;&#xC11C;&#xB4DC;</li>
          <li>Object.entiries &#xBA54;&#xC11C;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>### 타입스크립트 특징

 타입스크립트는 자바스크립트를 보완해 변수나 함수 등에 명시적으로 타입을 추가할 수 있게 해 타입 안정성을 높인 프로그래밍 언어입니다. 또한, 모듈화 기능, 객체 지향 프로그래 지원, VS code에서의 도구 지원등이 좋습니다.

 또한, 타입스크립트는 대규모 어플리케이션 제작을 위해 설계되었으므로 다음과 같은 대규모 어플리케이션을 개발하기 위해 필요한 조건을 모두 만족해야 합니다.

1. 모듈화를 통한 모듈 간 낮은 결합도\(Coupling\)
2. 객체 지향 프로그래밍 지원 \(코드의 중복과 복잡도 감소\)
3. 코드 규모가 커져도 구조화를 갖춰 개발 가능

 이러한 점에서 타입스크립트는 다음과 같은 특징을 가지고 있으며 이는 대규모 어플리케이션 개발에 필수적으로 필요하다.

1. 모듈 시스템 - ES6 모듈과 네임스페이스 지원
2. 클래스와 인터페이스 지원
3. 타입 시스템 지원

### 컴파일링과 트랜스파일링

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#xCEF4;&#xD30C;&#xC77C;&#xB9C1; | Compiling</td>
      <td style="text-align:left">
        <p>&#xD55C; &#xC5B8;&#xC5B4;&#xC758; &#xC18C;&#xC2A4; &#xCF54;&#xB4DC;&#xB97C;
          &#xB2E4;&#xB978; &#xC5B8;&#xC5B4;&#xC758; &#xC18C;&#xC2A4;&#xCF54;&#xB4DC;&#xB85C;
          &#xBC14;&#xAFB8;&#xB294; &#xAC83;</p>
        <p>[&#xC608;&#xC2DC;] C&#xC5B8;&#xC5B4;&#xB97C; &#xCEF4;&#xD30C;&#xC77C;
          &#xD574;&#xC11C; &#xC5B4;&#xC148;&#xBE14;&#xB9AC;&#xC5B4;&#xB85C; &#xBCC0;&#xD658;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#xD2B8;&#xB79C;&#xC2A4;&#xD30C;&#xC77C;&#xB9C1; | Transpiling</td>
      <td
      style="text-align:left">
        <p>&#xD55C; &#xC5B8;&#xC5B4;&#xC758; &#xC18C;&#xC2A4; &#xCF54;&#xB4DC;&#xB97C;
          &#xBE44;&#xC2B7;&#xD55C; &#xCD94;&#xC0C1;&#xD654; &#xC218;&#xC900;&#xC758;
          &#xB2E4;&#xB978; &#xC5B8;&#xC5B4;&#xB85C; &#xBC14;&#xAFB8;&#xB294; &#xAC83;</p>
        <p>[&#xC608;&#xC2DC;] C&#xC5B8;&#xC5B4;&#xB97C; &#xD2B8;&#xB79C;&#xC2A4;&#xD30C;&#xC77C;&#xB9C1;&#xD574;&#xC11C;
          Java&#xB85C; &#xBCC0;</p>
        </td>
    </tr>
  </tbody>
</table> 타입스크립트는 tsc라는 타입스크립트 컴파일러\(Typescript Compiler\)를 통해서 ECMA스크립트의 표준 언어로 컴파일됩니다. tsc는 타입스크립트를 설치하면 자동으로 함께 설치됩니다.

