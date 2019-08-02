# Console 메소드 유용하게 사용하기

## Console 객체

 window의 내장 객체 중 에러를 확인하고 해당 프로그램이 잘되는지 확인하기 위해 자바스크립트 개발자는 주로 console.log\(\)를 이용합니다. 하지만, console 객체에는 유용한 다양한 기능이 숨겨져 있습니다.

### console.log\(\)

```javascript
const name = "Stark";
const major = "Programmer";
console.log(name);
console.log(name, major);
console.log('%s 는 이름 %s는 전공입니다.', name, major);
```

 여기서 주의할 점은 자바스크립트에서도 C언어와 같이 %d, %s이런 치환 문법을 사용할 수 있습니다. 이와 비슷한 방식으로 warn, info, error 메소드가 있습니다.

| 구분  | 설명  |
| :--- | :--- |
| console.log\('기본'\) | 자주 사용하는 콘솔창에 보여주는 console 객체의 메소드입니다. |
| console.info\('정보'\) | 콘솔창에서 정보를 보여주는 console 객체의 메소드입니다. |
| console.warn\('경고'\) | 콘솔창에서 경고를 나타내는 console 객체의 메소드입니다. \[노란색\] |
| console.error\('에러'\) | 콘솔창에 에러를 나타내는 console 객체의 메소드입니다. \[빨간색\] |

 로깅을 할 때 매번 같은 로깅창을 보여주면 지루할 수 있고 또한 자신만의 에러 테스트를 위해 위와 같은 메소드를 사용할 수 있습니다.

{% hint style="info" %}
객체는 메모리를 참조하기 때문에 console.log를 통해 로깅을 할 경우 객체의 내용에 변경사항이 실시간으로 업데이트 됩니다. 즉, console.log이후에 데이터가 변해도 해당 값이 console.log에 적용됩니다.
{% endhint %}

{% hint style="info" %}
따라서 위와 같은 상황을 방지하기 위해서는 객체를 깊은 복사를 해서 로깅해주던가, 객체가 아닌 값을 로깅해주는 방식을 사용해야합니다. 하지만 비용절감상 객체가 아닌 값을 로깅해주는 방식이 선호됩니다. 
{% endhint %}

### console.dir\(\)

 console.dir\(object\)로 사용되며 자바스크립트 객체의 속성들을 한꺼번에 출력해주는 메소드입니다. 객체를 로깅하고 싶을 때는 보통 console.dir\(\)을 사용하는 것이 좋습니다.

```javascript
console.dir(object);
```

### console.count\(\)

 몇 번 호출되었는지를 로깅하고 싶을 때 사용하며 인자는 카운터의 이름으로 사용됩니다.

```javascript
console.count('첫번째 로깅');    //'첫번째 로깅 : 1'
console.count('두번째 로깅');    //'두번째 로깅 : 2'
console.count('세번째 로깅');    //'세번째 로깅 : 3'
console.count('네번째 로깅');    //'네번째 로깅 : 4'
```

### console.time\(\)과 console.timeEnd\(\)

 코드의 수행 시간을 확인할 때 유용한 로그입니다. 인자는 타이머의 이름입니다. 

time과 timeEnd에 같은 인자\(타이머 이름\)을 넣어야 정상적으로 동작합니다.

```javascript
console.time('콘솔타이머');
(프로그램 코드 ...)
console.timeEnd('콘솔타이머');    // 콘솔타이머: 동작 시간 ms
```

### console.clear\(\)

 해당 코드는 자주 사용하지는 않지만 콘솔창이 복잡한 것을 싫어하는 저 같은 사람을 위한 메소드입니다. 이 메소드가 실행되기 이전에 로깅된 데이터를 전부 다 지웁니다. 

