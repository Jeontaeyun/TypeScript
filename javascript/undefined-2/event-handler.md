# 이벤트 핸들러와 리스너

## 이벤트 핸들러와 리스너  

 브라우저에서 방문객이 취하는 모든 동작을 이벤트라고 합니다. 가령, 클릭, 키보드 입력, 로딩 등등이 이벤트에 해당합니다.

### 이벤트 종류

 자바스크립트에서 지원하는 이벤트의 종류는 다음과 같습니다.

#### 마우스 이벤트 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>mouseover</b>
      </td>
      <td style="text-align:left">&#xB9C8;&#xC6B0;&#xC2A4;&#xAC00; &#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xC5D0;
        &#xC62C;&#xB77C;&#xAC14;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD558;&#xB294;
        &#xC774;&#xBCA4;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>mouseout</b>
      </td>
      <td style="text-align:left">&#xB9C8;&#xC6B0;&#xC2A4;&#xAC00; &#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xC5D0;
        &#xBC97;&#xC5B4;&#xB0AC;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD558;&#xB294;
        &#xC774;&#xBCA4;&#xD2B8;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>mousemove</b>
      </td>
      <td style="text-align:left">
        <p>&#xB9C8;&#xC6B0;&#xC2A4;&#xAC00; &#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;
          &#xC601;&#xC5ED;&#xC5D0;&#xC11C; &#xC6C0;&#xC9C1;&#xC77C; &#xB54C; &#xBC1C;&#xC0DD;&#xD558;&#xB294;
          &#xC774;&#xBCA4;&#xD2B8;</p>
        <p>&#xCEE4;&#xC11C;&#xC758; &#xC704;&#xCE58; &#xD655;&#xC778;&#xC5D0; &#xC720;&#xC6A9;&#xD558;&#xB2E4;(&#xC0AC;&#xC6A9;&#xC790;
          &#xB370;&#xC774;&#xD130;&#xB97C; &#xBAA8;&#xC744; &#xC218; &#xC788;&#xACA0;&#xB2E4;)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>click</b>
      </td>
      <td style="text-align:left">&#xB9C8;&#xC6B0;&#xC2A4;&#xAC00; &#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xB97C;
        &#xD074;&#xB9AD;&#xD588;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD558;&#xB294;
        &#xC774;&#xBCA4;&#xD2B8;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>dbclick</b>
      </td>
      <td style="text-align:left">&#xB9C8;&#xC6B0;&#xC2A4;&#xAC00; &#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xB97C;
        &#xC5F0;&#xC18D; &#xB450; &#xBC88; &#xD074;&#xB9AD; &#xD588;&#xC744; &#xB54C;
        &#xBC1C;&#xC0DD;&#xD558;&#xB294; &#xC774;&#xBCA4;&#xD2B8;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>contextMenu</b>
      </td>
      <td style="text-align:left">&#xB9C8;&#xC6B0;&#xC2A4; &#xC6B0;&#xCE21; &#xD074;&#xB9AD;&#xC2DC;, &#xCEE8;&#xD14D;&#xC2A4;&#xD2B8;
        &#xBA54;&#xB274;&#xAC00; &#xBCF4;&#xC774;&#xAE30; &#xC9C1;&#xC804;&#xC5D0;
        &#xBC1C;&#xC0DD;&#xD558;&#xB294; &#xC774;&#xBCA4;&#xD2B8;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>mousedown</b>
      </td>
      <td style="text-align:left">&#xB9C8;&#xC6B0;&#xC2A4; &#xD074;&#xB9AD;&#xC758; &#xC55E; &#xC808;&#xBC18;(&#xBC84;&#xD2BC;&#xC744;
        &#xB204;&#xB984;)&#xC5D0;&#xC11C; &#xBC1C;&#xC0DD;&#xD558;&#xB294; &#xC774;&#xBCA4;&#xD2B8;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>mouseup</b>
      </td>
      <td style="text-align:left">&#xB9C8;&#xC6B0;&#xC2A4; &#xD074;&#xB9AD;&#xC758; &#xB4A4; &#xC808;&#xBC18;(&#xBC84;&#xD2BC;&#xC744;
        &#xB5CC;)&#xC5D0;&#xC11C; &#xBC1C;&#xC0DD;&#xD558;&#xB294; &#xC774;&#xBCA4;&#xD2B8;</td>
    </tr>
  </tbody>
</table>{% hint style="info" %}
**HTML5의 드래그앤 드랍 이벤트**

HTML5 부터는 드래그앤 드랍 이벤트가 도입되었지만 이를 mousedown과 mouseup으로도 구현 가능하다. 
{% endhint %}

#### 키보드 이벤트 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>keypress</b>
      </td>
      <td style="text-align:left">
        <p>&#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xC5D0;&#xC11C; &#xD0A4;&#xBCF4;&#xB4DC;&#xB97C;
          &#xB20C;&#xB800;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>&#xB2E8;, SHIFT, ALT, CTRL, &#xBC29;&#xD5A5; &#xD0A4; &#xB4F1; &#xAE30;&#xB2A5;
          &#xD0A4;&#xB294; &#xC81C;&#xC678;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>keydown</b>
      </td>
      <td style="text-align:left">&#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xC5D0;&#xC11C; &#xD0A4;&#xAC00;
        &#xB20C;&#xB838;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>keyup</b>
      </td>
      <td style="text-align:left">&#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xC5D0;&#xC11C; &#xD0A4;&#xBCF4;&#xB4DC;&#xB97C;
        &#xB20C;&#xB800;&#xB2E4; &#xB5BC;&#xC5C8;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
  </tbody>
</table>#### 폼 이벤트 

| 구분  | 설명  |
| :--- | :--- |
| **focus** | 지정한 요소에 포커스가 갔을 때 발생하는 이벤 |
| **blur** | 지정한 요소에 포커스가 다른 요소로 이동되어 잃었을 때 발생하는 이벤 |
| **change** | 지정한 요소에 value 속성값이 바뀌고 포커스가 이동되었을 때 발생하는 이벤트  |
| **submit**  | 폼 제출 버튼을 눌렀을 때, 혹은 텍스트 필드에서 엔터키를 눌렀을 때 발생하는 이벤 |
| **reset** | 폼 요소에 취소 버튼을 눌렀을 때 발생하는 이벤트  |
| **select**  | 텍스트 필드 등의 텍스트를 선택했을 때 발생하는 이벤트  |

#### 문서\(Document\) / 창\(Window\) 이벤트 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>load</b>
      </td>
      <td style="text-align:left">&#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xC758; &#xD558;&#xC704; &#xC694;&#xC18C;&#xB97C;
        &#xBAA8;&#xB450; &#xB85C;&#xB529; &#xD588;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD558;&#xB294;
        &#xC774;&#xBCA4;&#xD2B8;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>unload</b>
      </td>
      <td style="text-align:left">
        <p>&#xD574;&#xB2F9; &#xD398;&#xC774;&#xC9C0;&#xB97C; &#xBC97;&#xC5B4;&#xB0A0;
          &#xB54C; &#xBC1C;&#xC0DD;&#xD558;&#xB294; &#xC774;&#xBCA4;&#xD2B8;</p>
        <p>&#xB2E4;&#xB978; &#xD398;&#xC774;&#xC9C0;&#xB85C;&#xC758; &#xB9C1;&#xD06C;
          &#xC774;&#xB3D9;, &#xBE0C;&#xB77C;&#xC6B0;&#xC800; &#xD0ED;/&#xCC3D;&#xC744;
          &#xB2EB;&#xC74C; &#xB4F1;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>DOMContentLoaded</b>
      </td>
      <td style="text-align:left">
        <p>HTML &#xBB38;&#xC11C;&#xB97C; &#xC77D;&#xACE0; DOM &#xD2B8;&#xB9AC; &#xAD6C;&#xCD95;&#xC744;
          &#xC644;&#xB8CC;&#xD560; &#xB54C; &#xBC1C;&#xC0DD;&#xD558;&#xB294; &#xC774;&#xBCA4;</p>
        <p>load&#xC640; &#xB2E4;&#xB974;&#xAC8C; &#xC774;&#xBBF8;&#xC9C0;, &#xC2A4;&#xD0C0;&#xC77C;
          &#xC2DC;&#xD2B8; &#xB4F1;&#xC744; &#xAE30;&#xB2E4;&#xB9AC;&#xC9C0; &#xC54A;&#xC74C;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>resize</b>
      </td>
      <td style="text-align:left">&#xC9C0;&#xC815;&#xB41C; &#xC694;&#xC18C;&#xC758; &#xD06C;&#xAE30;&#xAC00;
        &#xBCC0;&#xACBD;&#xB418;&#xC5C8;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD558;&#xB294;
        &#xC774;&#xBCA4;&#xD2B8;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>scroll </b>
      </td>
      <td style="text-align:left">
        <p>&#xD398;&#xC774;&#xC9C0; &#xC2A4;&#xD06C;&#xB864; &#xC774;&#xB3D9;&#xD560;
          &#xB54C; &#xBC1C;&#xC0DD;&#xD558;&#xB294; &#xC774;&#xBCA4;</p>
        <p>&#xC2A4;&#xD06C;&#xB864;&#xBC14;&#xB97C; &#xB4DC;&#xB798;&#xADF8;&#xD558;&#xAC70;&#xB098;
          &#xB610;&#xB294; &#xD0A4;&#xBCF4;&#xB4DC;(&#xC704;/&#xC544;&#xB798;/home/end
          &#xB4F1;) &#xB610;&#xB294; &#xB9C8;&#xC6B0;&#xC2A4; &#xD720; &#xC0AC;</p>
      </td>
    </tr>
  </tbody>
</table>#### 드래그 앤 드랍 이벤트

| 구분  | 설명  |
| :--- | :--- |
| **dragstart** |  |
| **drag** |  |
| **dragend** |  |
| **dragenter** |  |
| **dragover** |  |
| **dragleave** |  |
| **drop**  |  |

#### 기타 이벤트 

| 구분  | 설명  |
| :--- | :--- |
| **error** | 문서 객체가 로드되는 동안 문제가 발생하는 이벤트  |
| **hashchange** | 해시 변경시 발생하는 이벤트  |

####  

{% hint style="info" %}
**키보드 접근성**

이벤트를 등록할 경우에는 마우스가 없어도 접근\(작동\)할 수 있도록 해야합니다. 이것을 키보드 접근성이라고 합니다.
{% endhint %}

| 마우스 이벤트  | 키보드 대응 이벤트  |
| :--- | :--- |
| onmouseover | onfocus |
| onmouseout | onblur |
| onclick | Enter |

### 이벤트 버블링 

 DOM에서 이벤트가 발생할 때 **자식 요소에서 발생한 이벤트가 부모 요소에도 전달되는 현상**을 이벤트 버블링이라고 합니다. 

 이벤트 버블링을 제어하지 못하면 불필요한 이벤트가 발생해서 원하는 프로그래밍이 어려울 수 있습니다. 

### 이벤트 객체 e

 요소에 이벤트가 발생하면 해당 이벤트는 이벤트 객체를 이벤트 리스너의 인자로 넣어줍니다. 이 때, 이벤트 객체는 다양한 속성과 메소드를 가집니다. 

#### 공통된 이벤트 객체 메소드 

| 구분  | 설명  |
| :--- | :--- |
| **e.preventDefault\(\)** | 태그의 기본 동작을 하지 않게 막아주는 메소드  |
| **e.stopPropagation\(\)**  | 태그를 클릭 시 부모에게 이벤트가 전달되는 버블링을 막아주는 메소드  |
| **e.stopImmediatePropagation\(\)**   | 이벤트 버블링을 막음과 동시에 같은 이벤트의 다른 리스너에도 실행되지 않도록 하는 메소드  |

{% hint style="info" %}
**태그의 기본 동작** 

* a 요소를 클릭하면 해당 경로로 페이지 이동 
* 브라우저 화면에서 우측 마우스 버튼 클릭 시 ContextMenu 발생
* form 요소 내 submit 버튼 클릭 시 지정된 경로로 내용을 전송
{% endhint %}

