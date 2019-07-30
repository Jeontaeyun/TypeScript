# 함수 \| Function

## 자바스크립트의 함수 

  자바스크립트의 함수의 개념은 매우 중요합니다. 함수에 적용된 다양한 개념이 존재하기에 이에 대해 완벽하게 숙지해두는 것이 자바스크립트를 사용하는데 큰 도움이 될 것 입니다.

 _함수란 특정한 변수를 대입한 후 어떠한 연산에 의해 결과값을 출력하는 것을 말합니다_. 이러한 함수는 **function**이라는 키워드로 선언할 수 있습니다.

### 자바스크립트의 함수 선언과 함수 표현식 

 자바 스크립트의 함수를 선언하는 방식에는 다양한 방법이 있습니다. 대표적인 예로 아래와 같이 함수를 선언할 수 있습니다.

```javascript
function add(x, y) {
    return x+y;
}
```

 위와 같은 방식으로 함수를 만드는 것을 **함수 선언**이라고 합니다.

```javascript
var add = function(x,y){
    return x+y;
};
```

 반면 위와 같은 방식으로 함수를 만드는 것을 **함수 표현식**이라고 합니다. 이 둘의 차이점은 호스팅이라는 현상에서 확인할 수 있습니다. 

### 자바스크립트의 함수 호출 

 자바스크립트에서 함수를 호출하기 위해서는 함수의 이름에 소괄호\(\)를 붙이고 소괄호 안에  해당 함수에서 요구하는 인자를 넣어주면 됩니다.

```javascript
var add = function(parameter_01, parameter_02, ...){
    return (...)
}

add(argument_01, argument_02, ...);
```

### 인자와 매개변수 \| Argument and Parameter

 프로그래밍 학습을 할 때 인자와 매개변수라는 말을 자주 들을 수 있습니다. 위의 함수 호출 부분에서 확인할 수 있듯이 인자와 매개변수에는 차이가 있습니다.

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
        <p>&#xC778;&#xC790;</p>
        <p>Argument</p>
      </td>
      <td style="text-align:left">&#xD568;&#xC218;&#xB97C; &#xC120;&#xC5B8;&#xD55C; &#xD6C4; &#xD638;&#xCD9C;&#xD560;
        &#xB54C; &#xB9E4;&#xAC1C;&#xBCC0;&#xC218;&#xC758; &#xC790;&#xB9AC;&#xC5D0;
        &#xB123;&#xC5B4;&#xC8FC;&#xB294; &#xC2E4;&#xC9C8;&#xC801;&#xC778; &#xAC12;&#xC744;
        &#xC778;&#xC790;&#xB77C;&#xACE0; &#xD55C;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>&#xB9E4;&#xAC1C;&#xBCC0;&#xC218;</p>
        <p>Parameter</p>
      </td>
      <td style="text-align:left">&#xD568;&#xC218;&#xB97C; &#xC120;&#xC5B8;&#xD560; &#xB54C; &#xB098;&#xC911;&#xC5D0;
        &#xC778;&#xC790;&#xAC00; &#xB4E4;&#xC5B4;&#xC624;&#xB294; &#xBD80;&#xBD84;&#xC744;
        &#xBA85;&#xC2DC; &#xBD80;&#xBD84;&#xC744; &#xB9E4;&#xAC1C;&#xBCC0;&#xC218;&#xB77C;&#xACE0;
        &#xD55C;&#xB2E4;.</td>
    </tr>
  </tbody>
</table> 이 둘을 구분하여 이해하면, 새롭게 배우는 언어에서 모두 용어적 이해를 좀 더 빨리 할 수 있을 것이다.

### 그 외 

 자바스크립트에서 사용하는 함수의 개념에는 몇 가지 특징이 있다. 

* **return이 없는 함수는 자동적으로 undefined를 반환합니다.**
* return 이후에는 함수가 종료되기 때문에 실행되지 않습니다.
* **자바스크립트는 함수가 매개변수로 전달되어 변수의 역할을 할 수 있습니다.**

```javascript
const add = (x,y) => {
    return x+y;
}
const addOne = (data, add) => {
    return add(data+1);
}
// 위의 코드는 add 함수가 addOne의 인자로 들어가서 동작하는 것을 보여주는 코드입니다. 
```

