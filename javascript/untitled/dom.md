# DOM 객체

## DOM \| 도큐먼트 객체 모델 

 트리 형태의 Document 구조로 구성된 HTML의 문서 구조를 담고 있는 객체입니다. 계층적 구조를 가지고 이를 제어하기 위해서 DOM 객체에 포함된 메소드와 속성을 이용할 수 있습니다. document객체는 window.document로 쓸 수도 있지만 window를 생략하고 document만 사용해서 쓸 수도 있습니다.

### Node와 Element

 Node는 태그 노드와 텍스트 노드 전체를 가리키고, Element는 텍스트 노드를 제외하고, 흔히 생각하는 태그만 가리킵니다. 따라서 태그만 검색하고 싶을 때는 Element가 붙은 메소드를 선택해야합니다.

### 대표적인 DOM 객체 메소드 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xBA54;&#xC18C;&#xB4DC;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">document.getElementById(&#xC544;&#xC774;&#xB514;)</td>
      <td style="text-align:left">HTML&#xC5D0;&#xC11C; &#xD574;&#xB2F9; &#xC544;&#xC774;&#xB514;&#xB97C;
        &#xAC00;&#xC9C0;&#xB294; &#xD0DC;&#xADF8;&#xB97C; &#xC120;&#xD0DD;&#xD558;&#xB294;
        &#xBA54;&#xC18C;&#xB4DC;.</td>
    </tr>
    <tr>
      <td style="text-align:left">document.getElementsByClassName(&#xD074;&#xB798;&#xC2A4;)</td>
      <td style="text-align:left">HTML&#xC5D0;&#xC11C; &#xD574;&#xB2F9; &#xD074;&#xB798;&#xC2A4;&#xBA85;&#xC744;
        &#xAC00;&#xC9C0;&#xB294; &#xBAA8;&#xB4E0; &#xD0DC;&#xADF8;&#xB97C; &#xC120;&#xD0DD;&#xD558;&#xB294;
        &#xBA54;&#xC18C;&#xB4DC;.</td>
    </tr>
    <tr>
      <td style="text-align:left">document.getElementsByName(&#xC774;&#xB984;)</td>
      <td style="text-align:left">HTML&#xC5D0;&#xC11C; &#xD574;&#xB2F9; &#xC774;&#xB984;&#xC744; &#xAC00;&#xC9C0;&#xB294;
        &#xBAA8;&#xB4E0; &#xD0DC;&#xADF8;&#xB97C; &#xC120;&#xD0DD;&#xD558;&#xB294;
        &#xBA54;&#xC18C;&#xB4DC;.</td>
    </tr>
    <tr>
      <td style="text-align:left">document.getElementsByTagName(&#xD0DC;&#xADF8;)</td>
      <td style="text-align:left">HTML&#xC5D0;&#xC11C; &#xD574;&#xB2F9; &#xD0DC;&#xADF8; &#xC774;&#xB984;&#xC744;
        &#xAC00;&#xC9C0;&#xB294; &#xBAA8;&#xB4E0; &#xD0DC;&#xADF8;&#xB97C; &#xC120;&#xD0DD;&#xD558;&#xB294;
        &#xBA54;&#xC18C;&#xB4DC;.</td>
    </tr>
    <tr>
      <td style="text-align:left">document.querySelector(&#xC120;&#xD0DD;&#xC790;)</td>
      <td style="text-align:left">
        <p>HTML&#xC5D0;&#xC11C; CSS &#xC120;&#xD0DD;&#xC790;&#xB97C; &#xD1B5;&#xD574;&#xC11C;
          &#xC5D8;&#xB9AC;&#xBA3C;&#xD2B8;&#xB97C; &#xC120;&#xD0DD;&#xD560; &#xC218;
          &#xC788;&#xB294; &#xBA54;&#xC18C;&#xB4DC;.</p>
        <p>CSS &#xC120;&#xD0DD;&#xC790;&#xB294; &#xAC70;&#xC758; &#xB2E4; &#xC4F8;&#xC218;
          &#xC788;&#xC2B5;&#xB2C8;&#xB2E4;. &#xB2E8;, &#xCD5C;&#xC0C1;&#xC704;&#xC758;
          &#xC5D8;&#xB9AC;&#xBA3C;&#xD2B8;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">document.querySelectorAll(&#xC120;&#xD0DD;&#xC790;)</td>
      <td style="text-align:left">HTML&#xC5D0;&#xC11C; CSS &#xC120;&#xD0DD;&#xC790;&#xB97C; &#xD1B5;&#xD574;&#xC11C;
        &#xC120;&#xD0DD;&#xB41C; &#xBAA8;&#xB4E0; &#xC5D8;&#xB9AC;&#xBA3C;&#xD2B8;&#xB97C;
        &#xBC18;&#xD658;&#xD558;&#xB294; &#xBA54;&#xC18C;&#xB4DC;.</td>
    </tr>
    <tr>
      <td style="text-align:left">document.createElement(&#xD0DC;&#xADF8;&#xBA85;)</td>
      <td style="text-align:left">
        <p>Document&#xAD6C;&#xC870;&#xC5D0; &#xC0C8;&#xB85C;&#xC6B4; &#xD0DC;&#xADF8;&#xB97C;
          &#xB9CC;&#xB4E4;&#xC8FC;&#xB294; &#xBA54;&#xC18C;&#xB4DC;.</p>
        <p>&#xB2E4;&#xB9CC; &#xBCC0;&#xC218;&#xD615;&#xD0DC;&#xB85C; &#xB9CC;&#xB4E4;&#xC5B4;
          &#xB450;&#xACE0; &#xC774;&#xB97C; Document&#xC5D0; &#xCD94;&#xAC00;&#xD558;&#xB294;
          &#xBA54;&#xC18C;&#xB4DC;&#xB294; &#xB530;&#xB85C; &#xC788;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">document.createTextNode(&#xD14D;&#xC2A4;&#xD2B8;)</td>
      <td style="text-align:left">
        <p>&#xD0DC;&#xADF8; &#xBFD0;&#xB9CC; &#xC544;&#xB2C8;&#xB77C; &#xD14D;&#xC2A4;&#xD2B8;&#xB3C4;
          &#xD568;&#xAED8; &#xB9CC;&#xB4E4;&#xC5B4;&#xC8FC;&#xB294; &#xBA54;&#xC18C;&#xB4DC;.</p>
        <p>&#xBCC0;&#xC218;&#xB97C; &#xD1B5;&#xD574; &#xBA54;&#xBAA8;&#xB9AC;&#xC5D0;&#xB9CC;
          &#xC800;&#xC7A5;&#xB429;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">document.createDocumentFragment()</td>
      <td style="text-align:left">
        <p>Fake Document&#xB97C; &#xB9CC;&#xB4DC;&#xB294; &#xBA54;&#xC18C;&#xB4DC;.</p>
        <p>&#xB9E4;&#xBC88; Document&#xB97C; &#xC9C1;&#xC811; &#xC870;&#xC791;&#xD558;&#xB294;
          &#xAC83; &#xBCF4;&#xB2E4; &#xC5EC;&#xAE30;&#xC5D0; &#xC800;&#xC7A5; &#xD6C4;
          &#xD55C;&#xBC88;&#xC5D0; Document&#xC5D0; &#xCD94;&#xAC00;&#xD558;&#xB294;
          &#xAC83;&#xC774; &#xC131;&#xB2A5; &#xBD80;&#xB2F4;&#xC774; &#xC904;&#xC5B4;&#xB4ED;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">document.&#xD0DC;&#xADF8;.appendChild()</td>
      <td style="text-align:left">createElement(), createTextNode(), createDocumentFragment()&#xB4F1;&#xC73C;&#xB85C;
        &#xC0DD;&#xC131;&#xB41C; &#xC694;&#xC18C;(Element)&#xB97C; &#xC9C0;&#xC815;&#xD55C;
        &#xD0DC;&#xADF8;&#xC758; &#xC790;&#xC2DD; &#xC694;&#xC18C;&#xB85C; &#xCD94;&#xAC00;&#xD574;&#xC8FC;&#xB294;
        &#xBA54;&#xC18C;&#xB4DC;.</td>
    </tr>
    <tr>
      <td style="text-align:left">document.&#xD0DC;&#xADF8;.removeChild()</td>
      <td style="text-align:left">&#xD574;&#xB2F9; &#xD0DC;&#xADF8;&#xC758; &#xC790;&#xC2DD; &#xD0DC;&#xADF8;&#xB97C;
        &#xC0AD;&#xC81C;&#xD558;&#xB294; &#xBA54;&#xC18C;&#xB4DC;</td>
    </tr>
    <tr>
      <td style="text-align:left">document.&#xBD80;&#xBAA8;&#xD0DC;&#xADF8;.insertBefore(&#xD0DC;&#xADF8;,
        &#xAE30;&#xC900;&#xD0DC;&#xADF8;)</td>
      <td style="text-align:left">&#xBD80;&#xBAA8; &#xD0DC;&#xADF8;&#xC758; &#xC790;&#xC2DD; &#xD0DC;&#xADF8;&#xB85C;
        &#xAE30;&#xC900; &#xD0DC;&#xADF8; &#xC774;&#xC804;&#xC758; &#xD615;&#xC81C;&#xD0DC;&#xADF8;&#xB85C;
        &#xC0BD;&#xC785;&#xD558;&#xB294; &#xBA54;&#xC18C;&#xB4DC;.</td>
    </tr>
    <tr>
      <td style="text-align:left">document.&#xD0DC;&#xADF8;.cloneNode()</td>
      <td style="text-align:left">&#xC790;&#xC2E0;&#xC744; &#xBCF5;&#xC0AC;&#xD558;&#xB294; &#xBA54;&#xC18C;&#xB4DC;.
        <br
        />&#xBCF5;&#xC0AC;&#xD55C; &#xAC83;&#xC744; &#xC800;&#xC7A5;&#xD574;&#xC11C;
        appendChild&#xB098; insertBefore&#xB85C; &#xC0BD;&#xC785;&#xD55C;&#xB2E4;.</td>
    </tr>
  </tbody>
</table>### 대표적인 DOM 속성 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xC18D;&#xC131;</th>
      <th style="text-align:left">&#xC124;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">document.head</td>
      <td style="text-align:left">Document&#xC758; HTML&#xC758; head&#xC5D0; &#xC811;&#xADFC;&#xD560; &#xC218;
        &#xC788;&#xB294; &#xC18D;&#xC131;</td>
    </tr>
    <tr>
      <td style="text-align:left">document.body</td>
      <td style="text-align:left">Document&#xC758; HTML&#xC758; body&#xC5D0; &#xC811;&#xADFC;&#xD560; &#xC218;
        &#xC788;&#xB294; &#xC18D;&#xC131;</td>
    </tr>
    <tr>
      <td style="text-align:left">document.title</td>
      <td style="text-align:left">
        <p>Document&#xC758; HTML&#xC758; title&#xC5D0; &#xC811;&#xADFC;&#xD560; &#xC218;
          &#xC788;&#xB294; &#xC18D;&#xC131;</p>
        <p>document.title = &quot;&#xB0B4;&#xC6A9;&quot;&#xC744; &#xD1B5;&#xD574;&#xC11C;
          &#xD0C0;&#xC774;&#xD2C0;&#xC744; &#xBC14;&#xAFC0; &#xC218;&#xB3C4; &#xC788;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">document.anchors</td>
      <td style="text-align:left">Document&#xC758; HTML&#xC758; anchors&#xC5D0; &#xC811;&#xADFC;&#xD560;
        &#xC218; &#xC788;&#xB294; &#xC18D;&#xC131;</td>
    </tr>
    <tr>
      <td style="text-align:left">document.links</td>
      <td style="text-align:left">Document&#xC758; HTML&#xC758; links&#xC5D0; &#xC811;&#xADFC;&#xD560; &#xC218;
        &#xC788;&#xB294; &#xC18D;&#xC131;</td>
    </tr>
    <tr>
      <td style="text-align:left">document.forms</td>
      <td style="text-align:left">Document&#xC758; HTML&#xC758; forms&#xC5D0; &#xC811;&#xADFC;&#xD560; &#xC218;
        &#xC788;&#xB294; &#xC18D;&#xC131;</td>
    </tr>
    <tr>
      <td style="text-align:left">document.images</td>
      <td style="text-align:left">Document&#xC758; HTML&#xC758; images&#xC5D0; &#xC811;&#xADFC;&#xD560;
        &#xC218; &#xC788;&#xB294; &#xC18D;&#xC131;</td>
    </tr>
    <tr>
      <td style="text-align:left">document.scrips</td>
      <td style="text-align:left">Document&#xC758; HTML&#xC758; scrips&#xC5D0; &#xC811;&#xADFC;&#xD560;
        &#xC218; &#xC788;&#xB294; &#xC18D;&#xC131;</td>
    </tr>
    <tr>
      <td style="text-align:left">document.&#xD0DC;&#xADF8;.nodeType</td>
      <td style="text-align:left">Document &#xD0DC;&#xADF8;&#xC758; &#xC885;&#xB958;&#xB97C; &#xC54C;&#xB824;&#xC8FC;&#xB294;
        &#xC22B;&#xC790;&#xB97C; &#xBC18;&#xD658;&#xD558;&#xB294; &#xC18D;</td>
    </tr>
    <tr>
      <td style="text-align:left">document.&#xD0DC;&#xADF8;.children</td>
      <td style="text-align:left">&#xC790;&#xC2DD; &#xB178;&#xB4DC;&#xB85C; &#xAC08; &#xB54C; &#xC0AC;&#xC6A9;&#xD558;&#xB294;
        &#xC18D;&#xC131;. &#xC774;&#xB54C; &#xD14D;&#xC2A4;&#xD2B8; &#xB178;&#xB4DC;&#xB294;
        &#xC81C;&#xC678;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">document.&#xD0DC;&#xADF8;.childNodes</td>
      <td style="text-align:left">&#xC790;&#xC2DD; &#xB178;&#xB4DC;&#xB85C; &#xAC08; &#xB54C; &#xC0AC;&#xC6A9;&#xD558;&#xB294;
        &#xC18D;&#xC131;. &#xC774; &#xB54C; &#xD14D;&#xC2A4;&#xD2B8; &#xB178;&#xB4DC;&#xB97C;
        &#xD3EC;&#xD568;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">document.&#xD0DC;&#xADF8;.firstChild</td>
      <td style="text-align:left">&#xCCAB; &#xBC88;&#xC9F8; &#xC790;&#xC2DD;&#xB9CC; &#xC120;&#xD0DD;&#xD558;&#xACE0;
        &#xC2F6;&#xC744; &#xB54C; firstChild &#xC18D;&#xC131;&#xC744;&#xC0AC;&#xC6A9;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">document.&#xD0DC;&#xADF8;.firstElementChild</td>
      <td style="text-align:left">
        <p>&#xCCAB; &#xBC88;&#xC9F8; &#xC790;&#xC2DD;&#xB9CC; &#xC120;&#xD0DD;&#xD558;&#xACE0;
          &#xC2F6;&#xC744; &#xB54C; firstElementChild&#xB97C; &#xC0AC;&#xC6A9;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>&#xB2E8;, &#xD14D;&#xC2A4;&#xD2B8; &#xB178;&#xB4DC;&#xB97C; &#xC81C;&#xC678;&#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">document.&#xD0DC;&#xADF8;.lastChild</td>
      <td style="text-align:left">&#xB9C8;&#xC9C0;&#xB9C9; &#xC790;&#xC2DD;&#xB9CC; &#xC120;&#xD0DD;&#xD558;&#xACE0;
        &#xC2F6;&#xC744; &#xB54C; &#xC0AC;&#xC6A9;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">document.&#xD0DC;&#xADF8;.lastElementChild</td>
      <td style="text-align:left">
        <p>&#xB9C8;&#xC9C0;&#xB9C9; &#xC790;&#xC2DD;&#xB9CC; &#xC120;&#xD0DD;&#xD558;&#xACE0;
          &#xC2F6;&#xC744; &#xB54C; &#xC0AC;&#xC6A9;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>&#xB2E8;, &#xD14D;&#xC2A4;&#xD2B8; &#xB178;&#xB4DC; &#xC81C;&#xC678;&#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">document.&#xD0DC;&#xADF8;.parentNode</td>
      <td style="text-align:left">&#xBD80;&#xBAA8; &#xC694;&#xC18C;&#xB97C; &#xCC3E;&#xC744; &#xB54C; &#xC0AC;&#xC6A9;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">document.&#xD0DC;&#xADF8;.parentElement</td>
      <td style="text-align:left">
        <p>&#xBD80;&#xBAA8; &#xC694;&#xC18C;&#xB97C; &#xCC3E;&#xC744; &#xB54C; &#xC0AC;&#xC6A9;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>&#xB2E8;, &#xD14D;&#xC2A4;&#xD2B8; &#xB178;&#xB4DC;&#xB97C; &#xC81C;&#xC678;&#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
  </tbody>
</table>### 대표적인 태그 속성

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xC18D;&#xC131;</th>
      <th style="text-align:left">&#xC124;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#xD0DC;&#xADF8;.&#xC18D;&#xC131;</td>
      <td style="text-align:left">
        <p>&#xD0DC;&#xADF8;&#xB97C; &#xC120;&#xD0DD;&#xD558;&#xACE0; &#xADF8; &#xC18D;&#xC131;&#xC744;
          &#xC870;&#xD68C;&#xD560; &#xC218; &#xC788;&#xACE0;, &#xBC14;&#xAFC0; &#xC218;&#xB3C4;
          &#xC788;&#xC2B5;&#xB2C8;&#xB2E4;.</p>
        <p>id, className(class), placeholder, checked, disabled, readonly &#xAC19;&#xC740;
          &#xC18D;&#xC131; &#xAC12;&#xC744; &#xBCFC; &#xC218; &#xC788;&#xC2B5;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#xD0DC;&#xADF8;.attributes</td>
      <td style="text-align:left">&#xD574;&#xB2F9; &#xD0DC;&#xADF8;&#xAC00; &#xAC00;&#xC9C4; &#xBAA8;&#xB4E0;
        &#xC18D;&#xC131;&#xC744; &#xBCFC; &#xC218; &#xC788;&#xC2B5;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xD0DC;&#xADF8;.clientHeight</td>
      <td style="text-align:left">&#xD0DC;&#xADF8;&#xC758; margin, border, scrollbar&#xB97C; &#xC81C;&#xC678;&#xD55C;
        &#xB192;&#xC774;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xD0DC;&#xADF8;.clientWidth</td>
      <td style="text-align:left">&#xD0DC;&#xADF8;&#xC758; margin, border, scrollbar&#xB97C; &#xC81C;&#xC678;&#xD55C;
        &#xB108;&#xBE44;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xD0DC;&#xADF8;.offsetHeight</td>
      <td style="text-align:left">&#xD0DC;&#xADF8;&#xC758; margin&#xB9CC; &#xC81C;&#xC678;&#xD55C; &#xB192;&#xC774;&#xB97C;
        &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xD0DC;&#xADF8;.offsetWidth</td>
      <td style="text-align:left">&#xD0DC;&#xADF8;&#xC758; margin&#xB9CC; &#xC81C;&#xC678;&#xD55C; &#xB108;&#xBE44;&#xB97C;
        &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xD0DC;&#xADF8;.scrollHeight</td>
      <td style="text-align:left">&#xC2A4;&#xD06C;&#xB864; &#xAC00;&#xB2A5;&#xD55C; &#xBC94;&#xC704; &#xAE4C;&#xC9C0;
        &#xD3EC;&#xD568;&#xD55C; &#xD0DC;&#xADF8;&#xC758; &#xB192;&#xC774;&#xB97C;
        &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xD0DC;&#xADF8;.scrollWidth</td>
      <td style="text-align:left">&#xC2A4;&#xD06C;&#xB864; &#xAC00;&#xB2A5;&#xD55C; &#xBC94;&#xC704; &#xAE4C;&#xC9C0;
        &#xD3EC;&#xD568;&#xD55C; &#xD0DC;&#xADF8;&#xC758; &#xB108;&#xBE44;&#xB97C;
        &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
  </tbody>
</table>### Data Attribute와 Dataset

 HTML5 부터 도입된 것으로 태그에 "data-"이름으로 시작하는 속성\(attribute\)을 삽입하면, 해당 컴포넌트 DOM 객체를 받아와서 다음과 같이 사용할 수 있다.

| 메소드 | 설 |
| :--- | :--- |
| 객체.data\(이름\) | data-이름 으로 시작된 태그의 속성값을 참조하는 메소드 |
| 객체.dataset | data-이름으로 시작된 태그의 속성값들을 반환하는 메소 |

