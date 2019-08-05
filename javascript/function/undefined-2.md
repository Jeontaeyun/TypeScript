# 클로저와 호이스팅

## 클로저와 호이스팅 

### 함수 호이스팅 \| Function Hoistitng

 **호이스팅은** **변수를 선언하고 초기화 했을 때 변수의 선언문을 유효 범위\(Scope\)의 최상단으로 끌어올리는 행위입니다**. 다음 예제를 통해서 확인할 수 있습니다.

```javascript
console.log(name);
sayHello();
function sayHello(){
    console.log('Hello my name is stark);
}
var name = stark;
```

 위의 코드는 순서상 위의 두 코드가 에러가 발생해야 합니다. 하지만, 실행 컨텍스트의

 반면 아래와 같이 함수 표현식을 통해 선언한 경우에는 호이스팅이 발생하지 않습니다.

```javascript
sayHello();                    // ERROR
const sayHello = function(){
    console.log('Hello');
}
```

### 클로저 \| Closure

