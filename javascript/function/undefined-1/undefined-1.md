# 자바스크립트의 상속

## 자바스크립트의 상속 

 상속은 객체 지향 프로그래밍의 꽃이라고 할 수 있습니다. 자바스크립트의 상속을 통해서 우리는 객체의 재사용성을 높일 수 있고 더 편한 개발이 가능하게 됩니다.

 자바스크립트에서는 상속을 하는 다양한 방법이 존재하지만, 에러가 제일 발생하지 않는 방법을 따르는 것이 낫습니다.

 또한, ES+부터는 자바스크립트에도 class 키워드를 사용할 수 있기에 이 방법을 사용하든 class 키워드를 사용하든 선택할 수 있습니다.

```javascript
function Dog(name, age){
    this.name = name;
    this.age = age;
}
Dog.prototype.bark = function(){
    console.log("bow bow I'm" + this.name);
}

function Jindo(name, age, type) {
    // 부모 요소를 자식 요소에 상속하는 방법 
    // Dog.apply(this, arguments);
    // this 는 Dog 객체의 값이고 , arguments는 이 함수에 들어온 매개변수이다. 
    Dog.apply(this, arguments);
    this.type = type;
}
Jindo.prototype = Object.create(Dog.prototype);
Jindo.prototype.constructor = Jindo;
// 자식 객체에 새로운 메소드를 추가하는 방법
Jindo.prototype.selfIntroduce = function(){
    console.log("My age is"+ this.age + "and my type is" + this.type);
}

const jindo = new Jindo('stark',25,'jindoDog');
jindo.selfIntroduce();
jindo.bark();

```

| 구분  | 설명  |
| :--- | :--- |
| **parentObject.apply\(this, arguments\)** | parentObject의 this를 그대로 받는 메소드. argument는 매개 변수를 의미합니다. 즉, 자식 요소에서 받은 인자를 Dog에 적용해서 생성하라는 의미입니다. |
| **Object.create\(someObject.prototype\)** | 객체를 만들되 생성자는 실행하지 않는 방법, 그냥 프로토타입만 생성해준다. |
| **someObject.prototype.constructor = someObject** | 자식 객체에서 부모 객체를 상속받은 후 자식 요소의 생성자는 부모 객체로 바뀌는데 이를 다시 자식 객체로 바꿔주는 방법 |

{% hint style="info" %}
**arguments 키워드** 

함수 안에서 arguments 키워드는 해당 함수에 들어온 매개변수들을 객체의 형태로 저장된 객체를 반환한다. 
{% endhint %}

