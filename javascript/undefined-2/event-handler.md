# 이벤트 핸들러와 리스너

## 이벤트 핸들러와 리스너  

 브라우저에서 방문객이 취하는 모든 동작을 이벤트라고 합니다. 가령, 클릭, 키보드 입력, 로딩 등등이 이벤트에 해당합니다.

### 이벤트 종류

 자바스크립트에서 지원하는 이벤트의 종류는 다음과 같습니다.

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">onmouseover</td>
      <td style="text-align:left">&#xB9C8;&#xC6B0;&#xC2A4;&#xAC00; &#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xC5D0;
        &#xC62C;&#xB77C;&#xAC14;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">onmouseout</td>
      <td style="text-align:left">&#xB9C8;&#xC6B0;&#xC2A4;&#xAC00; &#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xC5D0;
        &#xBC97;&#xC5B4;&#xB0AC;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">onmousemove</td>
      <td style="text-align:left">&#xB9C8;&#xC6B0;&#xC2A4;&#xAC00; &#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;
        &#xC601;&#xC5ED;&#xC5D0;&#xC11C; &#xC6C0;&#xC9C1;&#xC77C; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">onclick</td>
      <td style="text-align:left">&#xB9C8;&#xC6B0;&#xC2A4;&#xAC00; &#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xB97C;
        &#xD074;&#xB9AD;&#xD588;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">ondbclick</td>
      <td style="text-align:left">&#xB9C8;&#xC6B0;&#xC2A4;&#xAC00; &#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xB97C;
        &#xC5F0;&#xC18D; &#xB450; &#xBC88; &#xD074;&#xB9AD; &#xD588;&#xC744; &#xB54C;
        &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">onkeypress</td>
      <td style="text-align:left">
        <p>&#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xC5D0;&#xC11C; &#xD0A4;&#xBCF4;&#xB4DC;&#xB97C;
          &#xB20C;&#xB800;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>&#xB2E8;, SHIFT, ALT, CTRL, &#xBC29;&#xD5A5; &#xD0A4; &#xB4F1; &#xAE30;&#xB2A5;
          &#xD0A4;&#xB294; &#xC81C;&#xC678;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">onkeydown</td>
      <td style="text-align:left">&#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xC5D0;&#xC11C; &#xD0A4;&#xAC00;
        &#xB20C;&#xB838;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">onkeyup</td>
      <td style="text-align:left">&#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xC5D0;&#xC11C; &#xD0A4;&#xBCF4;&#xB4DC;&#xB97C;
        &#xB20C;&#xB800;&#xB2E4; &#xB5BC;&#xC5C8;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">onfocus</td>
      <td style="text-align:left">&#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xC5D0; &#xD3EC;&#xCEE4;&#xC2A4;&#xAC00;
        &#xAC14;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">onblur</td>
      <td style="text-align:left">&#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xC5D0; &#xD3EC;&#xCEE4;&#xC2A4;&#xAC00;
        &#xB2E4;&#xB978; &#xC694;&#xC18C;&#xB85C; &#xC774;&#xB3D9;&#xB418;&#xC5B4;
        &#xC783;&#xC5C8;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">onchange</td>
      <td style="text-align:left">&#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xC5D0; value &#xC18D;&#xC131;&#xAC12;&#xC774;
        &#xBC14;&#xB00C;&#xACE0; &#xD3EC;&#xCEE4;&#xC2A4;&#xAC00; &#xC774;&#xB3D9;&#xB418;&#xC5C8;&#xC744;
        &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">onload</td>
      <td style="text-align:left">&#xC9C0;&#xC815;&#xD55C; &#xC694;&#xC18C;&#xC758; &#xD558;&#xC704; &#xC694;&#xC18C;&#xB97C;
        &#xBAA8;&#xB450; &#xB85C;&#xB529;&#xD588;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">onunload</td>
      <td style="text-align:left">&#xBB38;&#xC11C;&#xB97C; &#xB2EB;&#xAC70;&#xB098; &#xB2E4;&#xB978; &#xBB38;&#xC11C;&#xB85C;
        &#xC774;&#xB3D9;&#xD588;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">onsubmit</td>
      <td style="text-align:left">&#xD3FC; &#xC694;&#xC18C;&#xC5D0; &#xC804;&#xC1A1; &#xBC84;&#xD2BC;&#xC744;
        &#xB20C;&#xB800;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">onreset</td>
      <td style="text-align:left">&#xD3FC; &#xC694;&#xC18C;&#xC5D0; &#xCDE8;&#xC18C; &#xBC84;&#xD2BC;&#xC744;
        &#xB20C;&#xB800;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">onresize</td>
      <td style="text-align:left">&#xC9C0;&#xC815;&#xB41C; &#xC694;&#xC18C;&#xC758; &#xD06C;&#xAE30;&#xAC00;
        &#xBCC0;&#xACBD;&#xB418;&#xC5C8;&#xC744; &#xB54C; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">onerror</td>
      <td style="text-align:left">&#xBB38;&#xC11C; &#xAC1D;&#xCCB4;&#xAC00; &#xB85C;&#xB4DC;&#xB418;&#xB294;
        &#xB3D9;&#xC548; &#xBB38;&#xC81C;&#xAC00; &#xBC1C;&#xC0DD;&#xB418;&#xC5C8;&#xC744;
        &#xB300; &#xBC1C;&#xC0DD;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
  </tbody>
</table>{% hint style="info" %}
**키보드 접근성**

이벤트를 등록할 경우에는 마우스가 없어도 접근\(작동\)할 수 있도록 해야합니다. 이것을 키보드 접근성이라고 합니다.
{% endhint %}

| 마우스 이벤 | 키보드 대응 이벤 |
| :--- | :--- |
| onmouseover | onfocus |
| onmouseout | onblur |
| onclick | Enter |



