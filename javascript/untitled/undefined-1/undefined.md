# 객체지향 프로그래밍의 다형성

## 오버라이딩\(OverRiding\)과 오버로딩\(OverLoading\)

 객체 지향 프로그래밍에서 객체의 다형성과 관련된 중요한 개념으로 오버라이딩과 오버로딩이 있습니다. 

### 함수 오버로딩 \| OverLoading

오버로딩은 정적 타입을 가지는 객체 지향 언어에서 볼 수 있는 개념으로 _**선언한 함수가 여러 개의 매개변수 또는 다양한 자료형의 매개변수를 처리할 때 사용하는 기법**_입니다.



```java
void overload(){
    System.out.println("매개변수 없는 오버로드");
}
void overload(int i, int j){
    System.out.println("매개변수"+i+"그리고"+j);
}
void overlaod(string i){
    System.out.println(i);
}
```

 위와 같이 같은 overload 함수를 다양한 자료형과 매개변수에 따라 동작하도록 하는 것이 오버로딩입니다.

 자바스크립트에서 오버로딩을 지원하는 방법은 다음과 같습니다.

```javascript
function overload(a,b,c){
    if(typeof c === 'function'){    // 문자열 두 개와 콜백
        c(a,b);
    }else if(typeof b === 'fucntion') { // 옵션 객체와 콜
        b(a);
    }else{
        a(); //콜백 하
    }
}
```

 위와 같은 방식으로 콜백을 제어하거나 프레임워크가 생겨나는 것이다.

### 객체 메소드 오버라이딩 \| OverRiding

_**상속 받은 부모의 메소드를 재정의하는 것을 의미**_합니다. 자바스크립트에서 오버라이딩의 개념을 존재하지만, 다른 언어와 다릅니다.

```javascript
const People = function() {};
People.prototype.hello = function(){
    console.log('안녕하세');
};

const Taeyun = function(){
    People.apply(this, arguments);    // 상
}
Taeyun.prototype = Object.create(People.prototype)
// 프로토타입 상속 
Taeyun.prototype.constructor = Taeyun // 상속을 위해

Taeyun.prototype.hello = function(name){
    console.log('안녕하세요 ' + name + '입니다.');
}
Taeyun.hello('전태윤');
// "안녕하세요 전태윤입니다."
```

매개변수가 자유롭고 리턴값의 자료형도 자유롭습니다. 

