# 함수 \| Function

## 자바스크립트의 함수 

  자바스크립트의 함수의 개념은 매우 중요합니다. 함수에 적용된 다양한 개념이 존재하기에 이에 대해 완벽하게 숙지해두는 것이 자바스크립트를 사용하는데 큰 도움이 될 것 입니다.

 _함수란 특정한 변수를 대입한 후 어떠한 연산에 의해 결과값을 출력하는 것을 말합니다_. 이러한 함수는 **function**이라는 키워드로 선언할 수 있습니다.

### 자바스크립트의 함수 선언과 함수 표현식 

 자바 스크립트의 함수를 선언하는 방식에는 다양한 방법이 있습니다. 대표적인 예로 아래와 같이 함수를 선언\(Statement\)할 수 있습니다.

```javascript
function add(x, y) {
    return x+y;
}
```

 위와 같은 방식으로 함수를 만드는 것을 **함수 선언\(Statement\)**이라고 합니다.

```javascript
var add = function(x,y){
    return x+y;
};
```

 반면 위와 같은 방식으로 함수를 만드는 것을 **함수 표현식\(Expression\)**이라고 합니다. 이 둘의 차이점은 호스팅이라는 현상에서 확인할 수 있습니다. 

### 자바스크립트의 함수 호출 

 자바스크립트에서 함수를 호출하기 위해서는 함수의 이름에 소괄호\(\)를 붙이고 소괄호 안에  해당 함수에서 요구하는 인자를 넣어주면 됩니다.

```javascript
var add = function(parameter_01, parameter_02, ...){
    return (...)
}

add(argument_01, argument_02, ...);
```

### 인자와 매개변수 \| Argument and Parameter

 프로그래밍 학습을 할 때 인자와 매개 변수라는 말을 자주 들을 수 있습니다. 위의 함수 호출 부분에서 확인할 수 있듯이 인자와 매개 변수 차이가 있습니다.

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
        &#xBA85;&#xC2DC; &#xBD80;&#xBD84;&#xC744; &#xB9E4;&#xAC1C;&#xBCC0;&#xC218;&#xB77C;
        &#xD55C;&#xB2E4;.</td>
    </tr>
  </tbody>
</table> 이 둘을 구분하여 이해하면, 새롭게 배우는 언어에서 모두 용어적 이해를 좀 더 빨리 할 수 있을 것이다.

{% hint style="info" %}
**함수의 Prototype**

 함수는 특수한 형태의 객체입니다. 생성될 때 기본적으로 자신과 동명의 객체를 생성하고 이를 prototype이란 속성으로 연결합니다. 

 즉, Stark라는 함수를 만들면 prototype은 Stark가 되고 이 동명의 객체가 함수의 프로토타입\(원형\) 객체입니다. 
{% endhint %}

### 화살표 함수 \| Arrow Function\(ES+\)

 화살표 함수는 ES2015부터 도입한 개념으로 구문이 짧고 자기 자신의 **this, arguments, super 또는 new.target등을 바인딩 하지 않습니다**. _즉, this를 호출하면 window 대신 상위 함수의 this를 가져 옵니다._ 

 화살표 함수는 항상 익명으로 이 함수 표현은 메소드 함수가 아닌 곳에 가장 적합합니다. 따라서 생성자로 사용할 수 없습니다. 

```javascript
const arrowFunction = () => {
        ...
};
```

{% hint style="info" %}
**자바스크립트 DOM 객체 이벤트 리스너**

자바스크립트와 제이쿼리에서 DOM 객체의 이벤트 리스너는 자동으로 this를 DOM 객체로 바꿉니다. 내부에서 자동으로 일어나는 작동이기에 어쩔 수 없이 암기해야 합니다. 

하지만, 이벤트 리스너 내부에서 만든 함수의 this는 window를 가리킵니다. 
{% endhint %}

### 매개변수 Default  및 rest \(ES+\)

#### 매개변수 Default

 ES2015+ 부터 매개변수에 초기값을 지정해주는 것이 가능해졌습니다.  다음과 같이 함수를 선언할 때 매개변수에 값을 대입해주면 기본값\(Default\)로 지정됩니다.

```javascript
function helloStark(x = 'hi' ,y = 'hello', z= 'stark' ){
    return console.log(x, y, z);
}
helloStark();
// 'hi hello stark'
```

#### 매개변수 rest

 ES2015+에서는 몇 개의 매개변수를 넣을 지 모를 때를 대비해 rest기능을 추가하였습니다. 다음과 같이 쓸 수 있습니다.

```javascript
const restPara = (x, y, ...rest){
    console.log(rest.length);        
    // rest = [3,4,5]
};
restPara(1,2,3,4,5);
// 3
```

단, 주의할 점은 rest를 생성할 때는 함수 매개변수의 가장 마지막 부분에 추가해야합니다.

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

