# 배열 \| Array

## 배열 \| Array

 자바스크립트의 배열은 자료구조의 연결리스트, 배열, 큐, 스택 등 다양하게 사용할 수 있는 만능 배열입니다. 따라서 정말 많이 사용되기에 배열에 관련된 메소드는 반드시 알아두어야 합니다.

### 배열 관련 메소드

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.length</td>
      <td style="text-align:left">&#xBB38;&#xC790;&#xC5F4;&#xACFC; &#xAC19;&#xC774; &#xBC30;&#xC5F4;&#xC758;
        &#xAE38;&#xC774;&#xB97C; &#xC54C;&#xB824;&#xC8FC;&#xB294; &#xC18D;&#xC131;&#xC785;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.join(&#xAD6C;&#xBD84;&#xC790;)</td>
      <td style="text-align:left">&#xBC30;&#xC5F4;&#xC758; &#xD56D;&#xBAA9;&#xC744; &#xAD6C;&#xBD84;&#xC790;&#xB97C;
        &#xAE30;&#xC900;&#xC73C;&#xB85C; &#xD569;&#xCE5C; &#xC0C8; &#xBB38;&#xC790;&#xC5F4;&#xB85C;
        &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;. &#xAD6C;&#xBD84;&#xC790;&#xB97C;
        &#xC785;&#xB825;&#xD558;&#xC9C0; &#xC54A;&#xC73C;&#xBA74; &#xC790;&#xB3D9;&#xC73C;&#xB85C;
        &#xC27C;&#xD45C;&#xB85C; &#xAD6C;&#xBD84;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.concat(&#xD569;&#xCE60; &#xAC83;)</td>
      <td style="text-align:left">&#xBC30;&#xC5F4;&#xC5D0; &#xC0C8;&#xB85C;&#xC6B4; &#xAC12;&#xC744; &#xD569;&#xCE5C;
        &#xC0C8;&#xB85C;&#xC6B4; &#xBC30;&#xC5F4;&#xC744; &#xC0DD;&#xC131;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.reverse()</td>
      <td style="text-align:left">&#xAE30;&#xC874;&#xC758; &#xBC30;&#xC5F4;&#xC758; &#xC21C;&#xC11C;&#xB97C;
        &#xC815; &#xBC18;&#xB300;&#xB85C; &#xB4A4;&#xC9D1;&#xC2B5;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.push(&#xD56D;&#xBAA9;)</td>
      <td style="text-align:left">&#xBC30;&#xC5F4;&#xC758; &#xB4A4;&#xC5D0; &#xC0C8;&#xB85C;&#xC6B4; &#xAC12;&#xC744;
        &#xCD94;&#xAC00;&#xD569;&#xB2C8;&#xB2E4;. &#xD574;&#xB2F9; &#xC791;&#xC5C5;
        &#xD6C4; &#xCD94;&#xAC00;&#xB41C; &#xAC12;&#xC744; &#xC801;&#xC6A9;&#xD55C;
        &#xBC30;&#xC5F4;&#xC758; &#xAE38;&#xC774;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.pop()</td>
      <td style="text-align:left">&#xB9C8;&#xC9C0;&#xB9C9; &#xC694;&#xC18C;&#xB97C; &#xC81C;&#xAC70;&#xD55C;
        &#xD6C4; &#xADF8; &#xC694;&#xC18C;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.unshift(&#xD56D;&#xBAA9;)</td>
      <td style="text-align:left">&#xBC30;&#xC5F4;&#xC758; &#xC55E;&#xC5D0; &#xC0C8;&#xB85C;&#xC6B4; &#xAC12;&#xC744;
        &#xCD94;&#xAC00;&#xD569;&#xB2C8;&#xB2E4;. &#xD574;&#xB2F9; &#xC791;&#xC5C5;
        &#xD6C4; &#xCD94;&#xAC00;&#xB41C; &#xAC12;&#xC744; &#xC801;&#xC6A9;&#xD55C;
        &#xBC30;&#xC5F4;&#xC758; &#xAE38;&#xC774;&#xB97C; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.shift()</td>
      <td style="text-align:left">&#xBC30;&#xC5F4;&#xC758; &#xC55E;&#xC5D0; &#xAC12;&#xC744; &#xBE7C;&#xB0C5;&#xB2C8;&#xB2E4;.
        &#xD574;&#xB2F9; &#xC791;&#xC5C5;&#xC73C;&#xB85C; &#xBE80; &#xAC12;&#xC744;
        &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.splice(&#xC2DC;&#xC791;&#xC810;, &#xC9C0;&#xC6B8; &#xAC1C;&#xC218;,
        &#xB123;&#xC744; &#xAC83;)</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.map((&#xAC12;, &#xC790;&#xB9BF;&#xC218;)=&gt;{return})</td>
      <td
      style="text-align:left">
        <p>&#xBC30;&#xC5F4;&#xC758; &#xC694;&#xC18C;&#xB9C8;&#xB2E4; &#xBC18;&#xBCF5;&#xBB38;&#xC744;
          &#xB3CC;&#xBA70; return &#xAC12;&#xC744; &#xAC00;&#xC9C0;&#xACE0; &#xC0C8;&#xB85C;&#xC6B4;
          &#xBC30;&#xC5F4;&#xC744; &#xB9CC;&#xB4E4;&#xC5B4;&#xC8FC;&#xB294; &#xD568;&#xC218;.</p>
        <p>&#xB2E8;, &#xBC30;&#xC5F4; &#xC548;&#xC5D0; &#xAC1D;&#xCCB4;&#xAC00; &#xC788;&#xC73C;&#xBA74;
          &#xADF8; &#xAC1D;&#xCCB4;&#xB294; &#xACF5;&#xC720;&#xB41C;&#xB2E4;.</p>
        </td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.forEach((&#xAC12;, &#xC790;&#xB9BF;&#xC218;)=&gt;{&#xC870;&#xAC74;})</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.reduce((&#xB204;&#xC801;&#xAC12;, &#xD604;&#xC7BF;&#xAC12;,
        &#xC778;&#xB371;&#xC2A4;, &#xC694;&#xC18C;)=&gt;{return},&#xCD08;&#xAE30;&#xAC12;)</td>
      <td
      style="text-align:left">&#xCD08;&#xAE30;&#xAC12;&#xACFC; &#xB204;&#xC801;&#xAC12;&#xC744; &#xD1B5;&#xD574;
        &#xBC30;&#xC5F4;&#xC758; &#xC694;&#xC18C;&#xB97C; &#xBC18;&#xBCF5;&#xD558;&#xBA70;
        &#xB3D9;&#xC791;&#xC744; &#xC218;&#xD589;&#xD558;&#xB294; &#xBA54;&#xC18C;&#xB4DC;.
        &#xBC18;&#xBCF5;&#xB418;&#xB294; &#xBAA8;&#xB4E0; &#xACF3;&#xC5D0; reduce&#xB97C;
        &#xC0AC;&#xC6A9;&#xD560; &#xC218; &#xC788;&#xC2B5;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.reduceRight</td>
      <td style="text-align:left">reduce&#xC640; &#xAC19;&#xC774; &#xC0AC;&#xC6A9;&#xD558;&#xC9C0;&#xB9CC;
        &#xBC30;&#xC5F4;&#xC758; &#xC694;&#xC18C;&#xB97C; &#xC624;&#xB978;&#xCABD;&#xC5D0;&#xC11C;
        &#xBD80;&#xD130; &#xC2DC;&#xC791;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.filter((&#xD56D;&#xBAA9;)=&gt;{&#xC870;&#xAC74;})</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.sort((&#xC774;&#xC804;&#xAC12;, &#xB2E4;&#xC74C;&#xAC12;)=&gt;{&#xC870;&#xAC74;})</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.indexOf(&#xCC3E;&#xC744; &#xAC83;)</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.lastIndexOf(&#xCC3E;&#xC744; &#xAC83;)</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.every((&#xD56D;&#xBAA9;) =&gt; {&#xC870;&#xAC74;})</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">&#xBC30;&#xC5F4;.some((&#xD56D;&#xBAA9;)=&gt;{&#xC870;&#xAC74;})</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Array.isArray(&#xAC12;)</td>
      <td style="text-align:left">Array&#xAC1D;&#xCCB4;&#xC758; static &#xBA54;&#xC18C;&#xB4DC;. &#xBC30;&#xC5F4;&#xC778;&#xC9C0;
        &#xC544;&#xB2CC;&#xC9C0; &#xD655;&#xC778;&#xD574;&#xC8FC;&#xB294; &#xC5ED;&#xD560;&#xC744;
        &#xD558;&#xBA70; true&#xC640; false&#xB85C; &#xAC12;&#xC744; &#xBC18;&#xD658;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
  </tbody>
</table>