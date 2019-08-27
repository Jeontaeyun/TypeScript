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

 MDN의 정의상 _"클로저는 독립적인 \(자유\)변수를 카리키는 함수이다.  또는 클로저 안에 정의된 함수는 만들어진 환경을 기억한다."_ 라고 정의되어 있습니다.

{% hint style="info" %}
**클로저**

클로저는 외부함수의 변수에 접근할 수 있는 내부함수입니다.

클로저는 세 가지 스코프 체인을 가집니다. 클로저 자기 자신에 대한 접근\(자신의 블락내에 정의된 변수\), 외부 함수의 변수에 대한 접근, 전역 변수에 대한 접근 
{% endhint %}

 흔히 **함수 내에서 함수를 정의하고 사용하면 클로저라고 합니다. 하지만 대부분 정의한 함수를 리턴하고 외부에서 사용하게 됩니다.** 

 클로저를 활용한 유명한 카운터 예제를 통해서 보면 클로저를 확인할 수 있다.

```javascript
const counter = function(){
    let count = 0;
    function changeCount(number){
        count += number;
    }
    return{
        increase: function(){
            changeCount(1);
        },
        decrease: function(){
            changeCount(-1);
        }
        show: function() {
            alert(count);
        }
    }
}
const counterClosure = counter();
counterClosure.increase();
counterClosure.show();            // 1
counterClosure.decrease();
counterClosure.show();            // 0
```

 클로저는 보통 2가지 경우를 위해서 사용한다.

1. 사이드 이펙트\(Side effects\) 제어하기
2. 비공개 변수\(Private\) 생성하기

#### 사이드 이펙트 제어하기 \| Side Effects

 함수에서 값을 반환할 때를 제외하고 무언가를 행할 때 사이드 이펙트\(Side Effects\)가 발생합니다. 

{% hint style="info" %}
**사이드 이펙트 \| Side Effects**

자바스크립트의 관점에서 사이드 이펙트는 자바스크립트 함수의 코드가 외부 세계에 영향을 주거나 받는 것이다. 

예를 들어 데이터 요청\(fecth\)등의 비동기 작업, 브라우저 캐시, AJAX, timeout을 생성할 때 생기는 것도 사이드 이펙트이다.

심지어 console.log를 선언하는 것도 사이드 이펙트이다.
{% endhint %}

#### 비공개 변수 활용 \| Private 

 이와 같은 방식을 사용하면 사용자는 개발자가 공개한 메소드만 사용할 수 잇습니다. 변수의 스코프 체인때문에 외부에서 count 변수에 접근할 수 없어 비공개 변수가 되지만 이 값을 오직 제공한 메소드를 통해서만 제어할 수 있습니다.

 이를 통해 사용자가 예상을 뒤엎는 행동을 하는 것을 막을 수 있습니다. 즉, 자바스크립트에서 사용자를 통제하기 위한 기본적인 방법이 바로 클로저입니다.

 단, 단점으로는 잘못 사용했을 시 성능 문제와 메모리 문제가 발생할 수 있습니다. 클로저의 비공개 변수는 자바스크립트에서 언제 메모리 관리를 해야할 지 모릅니다. 따라서 메모리 낭비가 발생할 수 있습니다. 

### 클로저 예시 

```javascript
const arr = [10, 12, 15, 21];
for(var i = 0; i < arr.length ; i++){
    setTimeout(function() {
        console.log('The index of ' + i );
    }, 3000);
}
// 모두 4 4 4 4가 찍힌다. 
```

 위의 문제는 자바스크립트의 특성을 이해해야 한다. 자바스크립트의 setTimeout함수는 인덱스 i를 반복하는 스코프 밖의 스코프를 갖는 클로저를 생성한다.

 이는 setTimeout\(\)의 스코프와 for 반복문의 안의 스코프가 다르기 때문에 발생하는 현상인다. 

#### 논리적 생각

1. for 반복문이 발생하며 i 는 올라간다.

2. setTimeout의 콜백 함수는 3초 뒤에 생성되고 내부에 스코프 체인에 i가 없으므로 외부의 스코프 체인 i를 참조하여 4를 4번 참조한다.

이를 해결하기 위해 다음과 같이 프로그래밍이 가능하다.

```javascript
const arr = [10, 12, 15, 21];
for(var i = 0; i < arr.length; i ++){
    setTimeout((function(i_local){
        return function(){
            // i를 하위 함수의 인자로 바인딩 해준다.
            console.log('The index of ' + i_local);
        }
    })(i), 3000);
}
```

```javascript
const arr = [10, 12, 15, 21];
//ES6의 let을 사용한다.
//ES6의 let은 함수가 호출될 때 마다 인덱스 i 값이 바인딩 된다. 
for(let i = 0; i < arr.length; i ++){
    setTimeout(function(){
         console.log('The index of ' + i );
    }, 3000);
}
```

