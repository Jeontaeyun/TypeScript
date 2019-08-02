# 쓰로틀링과 디바운싱

## 쓰로틀링과 디바운싱

 쓰로틀링과 디바운싱은 프로그래밍 기법 중 하나입니다. 즉, 특정한 동작을 하기 위해 사용되는 개념으로 프로그래밍 업계에서 일을 하기 위해 알아두면 좋은 용어입니다.

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
        <p>&#xC4F0;&#xB85C;&#xD2C0;&#xB9C1;</p>
        <p>Throttling</p>
      </td>
      <td style="text-align:left">&#xB9C8;&#xC9C0;&#xB9C9; &#xD568;&#xC218;&#xAC00; &#xD638;&#xCD9C;&#xB41C;
        &#xD6C4; &#xC77C;&#xC815; &#xC2DC;&#xAC04;&#xC774; &#xC9C0;&#xB098;&#xAE30;
        &#xC804;&#xC5D0; &#xB2E4;&#xC2DC; &#xD638;&#xCD9C;&#xB418;&#xC9C0; &#xC54A;&#xB3C4;&#xB85D;
        &#xD558;&#xB294; &#xD504;&#xB85C;&#xADF8;&#xB798;&#xBC0D; &#xAE30;&#xBC95;</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>&#xB514;&#xBC14;&#xC6B4;&#xC2F1;</p>
        <p>Debouncing</p>
      </td>
      <td style="text-align:left">&#xC5F0;&#xC18D;&#xC801;&#xC73C;&#xB85C; &#xD638;&#xCD9C;&#xB418;&#xB294;
        &#xD568;&#xC218;&#xB4E4; &#xC911; &#xB9C8;&#xC9C0;&#xB9C9; &#xD568;&#xC218;
        &#xD639;&#xC740; &#xAC00;&#xC7A5; &#xCC98;&#xC74C;&#xC758; &#xD568;&#xC218;&#xB9CC;
        &#xC2E4;&#xD589;&#xD558;&#xB3C4;&#xB85D; &#xD558;&#xB294; &#xD504;&#xB85C;&#xADF8;&#xB798;&#xBC0D;
        &#xAE30;</td>
    </tr>
  </tbody>
</table> 디바운싱은 주로 ajax 검색에 자주 사용되고, 쓰로틀링은 스크롤을 올리거나 내릴 때 주로 사용합니다. 

가령, 리덕스 사가를 이용한 비동기 처리를 할 때 스크롤을 인식해 데이터를 더 불러오는 인피니트 스크롤을 구현할 때 쓰로틀링을 사용하면 스크롤의 연속적인 값으로 인해 데이터를 호출하는 함수가 반복되는 것을 방지할 수 있습니다.

### 쓰로틀링 \| Throttling

### 디바운싱 \| Debouncing

