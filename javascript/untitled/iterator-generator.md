# 반복기와 생성기\(ES6\)

## 반복기와 생성기 

  최근 대부분의 언어들이 **반복\(loop\)에 대해 추상화된 방법과 인터페이스를 제공**하고 있습니다. 

이런 방식의 장점은 Array와 Map과 다르게 사용자 정의 **Object나 기본 동작이 없는 객체들도 동일하게 반복을 정의할 수 있다는 점** 입니다. 

자바스크립트 MDN 문서에서도 반복기와 생성기를 반복 개념을 핵심 언어 내로 가져와 for...of 루프의 동작을 사용자가 정의하는 메커니즘으로 제공한다고 설명되어 있습니다.



{% hint style="info" %}
**Iteration Protocol**

어떤 객체든 특정 조건을 만족하면 Iterable 또는 Iterator로 평가 받을 수 있도록 하는 규약

Iterable은 반복 가능한 객체를 의미하며 Iterable로 평가되면 **for..of**, **전개 문법\(Spread Syntax\)**, **구조 분해 할당\(Destructuring\)**등에 사용할 수 있다.
{% endhint %}

{% hint style="info" %}
**Iterable 객체가 되기 위한 사항**

01. 객체 내에 \[Symbol.iterator\]\(= @@iterator\) 메소드가 존재해야 한다.

02. \[Symbol.iterator\] 메서드는 Iterator 객체를 반환해야 한다.
{% endhint %}

### 반복기 \| Iterator

```javascript
const iterator = (data) => ({
    // 반복되는 규칙을 내부적으로 처리하는 것 Symbol키워드는 자바스크립트 내부를 접근할 수 있다. 
    [Symbol.iterator](){
    return{
        data,
        next() {
            return {
                done : this.data.length === 0,
                value : this.data.pop()  
            };
        }
    }
    }
});
for(const a of iterator([1,2,3]))console.log(a);
// 자동으로 1, 2, 3에 대해 출력해주는 작업을 3번 한다.
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">[Symbol.iterator]()</td>
      <td style="text-align:left">Iterator&#xB97C; &#xB9CC;&#xB4E4;&#xC5B4;&#xC8FC;&#xB294; &#xBA54;&#xC18C;&#xB4DC;
        &#xBC18;&#xB4DC;&#xC2DC; Iterator Object&#xB97C; &#xBC18;&#xD658;&#xD574;&#xC57C;&#xD569;&#xB2C8;&#xB2E4;</td>
    </tr>
    <tr>
      <td style="text-align:left">next()</td>
      <td style="text-align:left">
        <p>IteratorResultObject&#xB97C; &#xB9AC;&#xD134;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>IteratorResulltObject&#xB294; done&#xACFC; value&#xB97C; &#xAC16;&#xB294;
          &#xAC1D;&#xCCB4;&#xB85C; done&#xACFC; value&#xB97C; &#xAC00;&#xC9D1;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">done</td>
      <td style="text-align:left">&#xBC18;&#xBCF5;&#xC758; &#xC644;&#xB8CC; &#xC5EC;&#xBD80;&#xB97C; &#xD0C0;&#xB098;&#xB0C5;&#xB2C8;&#xB2E4;</td>
    </tr>
    <tr>
      <td style="text-align:left">value</td>
      <td style="text-align:left">&#xD604;&#xC7AC; &#xAC12;&#xC744; &#xC758;&#xBBF8;&#xD569;&#xB2C8;&#xB2E4;</td>
    </tr>
  </tbody>
</table>### 생성기 \| Generator

 Generator는 일반적으로 Iterator를 쉽게 구현하기 위해 나온 문법이다.

 생성기는 반복기가 한 번 생성하면 그저 무한히 반복하고 중간의 중단점을 만들어 주지 못한다는 불편함을 해결하기 위해 나왔습니다. 

 **PS. Generator함수는 화살표 함수를 이용해 정의할 수 없다.**

{% hint style="info" %}
**Coroutine \| 코루틴** 

 일반적인 함수는 외부 환경에서 단순히 값을 인자로 받아 return으로 종료된다. 코루틴은 여기에 return과 더불어 suspend/resume 기능을 실행할 수 있게해준다.   
즉, **중간의 실행을 중단하고 그 지점부터 다시 실행을 이어나가는 기능을 해준다.**
{% endhint %}

Generator문법은 iterator를 통해서 **코루틴을 만들어주는 역할**을한다.

* **yield**키워드를 통해서 suspend\(연기하다\)를 건다
* **next\(\)**가 호출되면 resume\(재개하다\)된다

{% hint style="info" %}
**async와 await과 같은 비동기처리**  
  
생성기의 suspend/resume 특성을 비용해 비동기 코드를 동기화 하여 사용할 수 있습니다. ES2017에서는 이런 특성을 이용한 async / await 키워드를 만들 었습니다. 하지만 이전 까지는 이런 방식으로 비동기 코드를 동기화 했습니다.
{% endhint %}

```javascript
fuction* generator() {
    console.log('1번 실행');
    yield 1;                    //yield는 중단점을 제공한다.
    console.log('2번 실행');
    yield 2;
    console.log('3번 실행');
    yield 3;
}

const gener = generator();

gener.next(); // 1번 실행, {value:1, done: false}
for (num of iter) console.log(num); // 2번실행, 2 , 3번 실행, 3
```

 위와 같이 **functionn\* 키워드**를 통해 생성기를 만들 수 있다.

