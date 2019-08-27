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

 매우 짧은 시간에 다수 발생하는 이벤트\(스크롤, 윈도우 크기 재조정 등 등\)를 처리할 때 이로 인해 발생하는 성능 저하를 막기 위해서 디바운싱을 사용해야 합니다. 

  아래는 바닐라 자바스크립트로 디바운싱을 구현한 것 입니다. 디바운싱의 올바른 구현 방법은 몇 가지 함수 호출을 한 개의 그룹으로 묶고 특정 시간이 지난 후에야만 호출 될 수 있도록 구조화 하는 것 입니다.

```javascript
function debounce(fn, delay){
    // 타이머 선언
    let timer = null;
    // 타이머 변수에 접근 가능한 클로저 함
    return function(){
        // 클로져 함수 안에서 this와 arguments 변수로 디바운싱 함수의 스코프와 변수를 접근한다. 
        let context = this;
        let args = arguments;
        //만약 이벤트가 호출되면 타이머를 초기화 하고 다시 시
        clearTimeout(timer);
        timer = setTimeout(function(){
            fn.apply(context, args);
            // fn 안의 this는 window일 것이다. 이벤트 리스너 안에서 쓰게 된다면 상위 이벤트 리스너의 this와
            // 다를 것이기 때문에 this를 바인딩 해주어야 한다. 
        },delay);
    }
}
```

