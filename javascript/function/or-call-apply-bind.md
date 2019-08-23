# 함수 메소드 \| call, apply, bind

## 함수 메소드

 기본적으로 자바스크립트의 함수는 특수한 형태의 객체이기에, 함수 객체를 위한 메소드가 존재한다. 대표적인 함수 메소드는 **call**, **apply**, **bind**이다.

```javascript
const example = function(a,b,c){
    return console.log(a,b,c);
}
example("hi","stark","jeon");
example.call(null, "hi","stark","jeon");
example.apply(null,["hi","stark","jeon"]);
```

 함수를 호출하는 방법은 기본적으로 `example("hi","starkt","jeon")`의 방식을 사용하지만, call과 apply의 방식으로 호출할 수 있다.

 이때, null 부분에 대체할 this를 넣어 함수의 this를 바꿀 수 있다. 이를 통해 다른 객체의 함수를 자유자재로 사용할 수 있다.



 bind 메소드는 함수가 가리키는 this만 바꾸고 호출하지 않는 메소드입니다. 

```javascript
const object_test = {
    name: "stark",
    greating: function(){
        alert(this.name);
    }
};
const object_bind ={
    name: "Taeyun"
};

const greating = object_test.greating.bind(object_bind);

greting(); // "Taeyun"

```

### Example Situation

 call, apply, bind를 자주 쓰는 예시는 유사배열을 배열로 바꿀 때 입니다. 유사 배열은 배열과 비슷한 형태를 가지지만 배열 메소드를 사용할 수  없는 객체를 말합니다.



대표적인 유사배열로 **arguments**가 있습니다. arguments는 함수라면 처음부터 가지고 있는 특별한 속성입니다. **함수로 들어온 인자를 유사 배열형식으로 반환**합니다.



```javascript
function example(){
    console.log(arguments);
    console.log(Array.proptotype.join.call(arguments);
}
example("hi", "string", "Taeyun"); // ["hi, "string", "Taeyun"]

```

위의 코드는 배열의 프로토타입 메소드인 join을 유사배열인 arguments를 통해 사용하는 방법입니다.

### TLDR

| 구분  | 설명  |
| :--- | :--- |
| call\(null, ...\); | this를 바꾸고 해당 함수를 호출하는 메소 |
| apply\(null, \[...\]\); | this를 바꾸고 해당 함수를 호출하는 메소 |
| bind\(this\); | 메소드 함수가 가리키는 this만 바꾸고 호출하지 않는 메소 |

