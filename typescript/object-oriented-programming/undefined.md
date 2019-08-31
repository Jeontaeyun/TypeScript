# 객체 지향 프로그래밍과 클래스

## 객체 지향 프로그래밍 

 **객체 지향 프로그래밍\(OOP, Object-Oriented Programming\)**은 애플리케이션을 개발할 때 코드 중복을 획기적으로 줄일 수 있는 방법입니다. 

 객체 지향 프로그래밍은 커다란 문제를 클래스라는 단위로 나누고 클래스 간의 관계를 추가하면서 코드 중복을 최소화하는 개발 방식입니다.

| 객체지향 프로그래밍 요소 | 자바스크립트\(ES6\) | 타입스크립트 |
| :--- | :--- | :--- |
| **클래스** | class  | class  |
| **인터페이스** | 지원 안함 | interface |
| **인터페이스 구현** | 지원 안함 | implements |
| **상속** | extends | extends |
| **생성자** | constructor\(\){} | constructor\(\){} |
| **접근 제한자** | 지원 안함 | private, public, protected |
| **final 제한자** | 지원 안함 | readonly \(TS 2.0부터 지원\) |
| **static 키워드** | static | static |
| **super 키워드**  | super | super |

### 접근 제한자 \| Access Modifier

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xC811;&#xADFC; &#xC81C;&#xD55C;&#xC790;</th>
      <th style="text-align:left">&#xD2B9;&#xC9D5;</th>
      <th style="text-align:left">&#xC0C1;&#xC18D; &#xC5EC;</th>
      <th style="text-align:left">&#xC678;&#xBD80; &#xAC1D;&#xCCB4; &#xC811;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>public</b>
      </td>
      <td style="text-align:left">public&#xC73C;&#xB85C; &#xC124;&#xC815;&#xB41C; &#xBA64;&#xBC84;(&#xBA64;&#xBC84;
        &#xBCC0;&#xC218;, &#xBA64;&#xBC84; &#xBA54;&#xC11C;&#xB4DC; &#xB4F1;)&#xB294;
        &#xC790;&#xC2DD; &#xD074;&#xB798;&#xC2A4; &#xBC0F; &#xC678;&#xBD80; &#xAC1D;&#xCCB4;&#xC5D0;&#xC11C;
        &#xC811;&#xADFC; &#xAC00;&#xB2A5;&#xD558;&#xB2E4;.</td>
      <td style="text-align:left">O</td>
      <td style="text-align:left">O</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>protected</b>
      </td>
      <td style="text-align:left">
        <p>protected&#xB85C; &#xC124;&#xC815;&#xB41C; &#xBA64;&#xBC84;&#xB294; &#xC790;&#xC2DD;
          &#xD074;&#xB798;&#xC2A4;&#xC5D0;&#xC11C; &#xC811;&#xADFC; &#xAC00;&#xB2A5;.</p>
        <p>&#xB2E8;, &#xC678;&#xBD80; &#xAC1D;&#xCCB4;&#xB97C; &#xD1B5;&#xD55C; &#xC811;&#xADFC;
          &#xBD88;&#xAC00;&#xB2A5;</p>
      </td>
      <td style="text-align:left">O</td>
      <td style="text-align:left">X</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>private</b>
      </td>
      <td style="text-align:left">private&#xC73C;&#xB85C; &#xC124;&#xC815;&#xB41C; &#xBA64;&#xBC84;&#xB294;
        &#xD604;&#xC7AC; &#xD074;&#xB798;&#xC2A4;&#xC5D0;&#xC11C;&#xB9CC; &#xC811;&#xADFC;&#xD560;
        &#xC218; &#xC788;&#xACE0;, &#xC790;&#xC2DD; &#xD074;&#xB798;&#xC2A4; &#xBC0F;
        &#xC678;&#xBD80; &#xAC1D;&#xCCB4;&#xC5D0;&#xC11C; &#xC811;&#xADFC; &#xBD88;&#xAC00;&#xB2A5;</td>
      <td
      style="text-align:left">X</td>
        <td style="text-align:left">X</td>
    </tr>
  </tbody>
</table> 생성자\(Constructor\)의 매개변수에 접근 제한자를 추가하여 멤버 변수를 만들 수 있습니다.  예시는 다음과 같습니다. 

```typescript
class Cons {
    public name : string;
    private age : number;
    protected job : string;
    constructor(name: string, age: number, job: string){
        this.name = name;
        this.age = age;
        this.job = job;
    }
}
```

 위의 코드를 아래와 같이 간단하게 할 수 있습니다. 

```typescript
class Cons{
    constructor(public name: string, private age: number, protected height: number){
    
    }
}
```

{% hint style="info" %}
**readonly** 

readonly는 선언한 변수를 읽기 전용 속성으로 만들며 상속이나 객체를 통한 외부 접근도 허용합니다. 
{% endhint %}

### 클래스 선언과 객체 생성 

 클래스는 설계 도면과 같고 설계 도면의 실제는 물건\(객체\)가 됩니다. 객체는 메모리에 존재하는 실제 데이터입니다. **클래스를 가지고 실제 객체를 만드는 것을 인스턴스화라고 하며 그 객체를 인스턴스라고 합니다**.

```typescript
class People {                 // 클래스(설계 도면) 기술하는 부
    ...
}
const Stark = new People();    // 인스턴스화로 객체 생성
```

### 상속관계와 포함관계

 객체 지향 프로그래밍에서 클래스 간의 관계를 크게 두 가지로 나눕니다.

* 상속 관계 \(Inheritance\) \| IS-A
  * 타입스크립트는 클래스에 대해 단일 상속만 지원한다. 
  * 자식 클래슥가 부모 클래스를 상속받을 때 생성자에서 super\(\)메소드를 호출해 부모 클래스의 생성자를 호출해야 합니다. 
* 포함 관계  \| HAS-A
  * 합성\(Composition\) 관계
  * 집합\(Aggregation\) 관계

#### 합성 관계



#### 집합 관계 



### 추상 클래스 Abstract Class

 추상 클래스\(Abstract Class\)는 **구현 메서드**와 **추상 메서드\(Abstract Method\)**가 동시에 존재하는 클래스를 말합니다.

| 구분  | 설명 |
| :--- | :--- |
| 구현 메서드 | 실제 구현 내용을 포함한 메서드 |
| 추상 메서드 | 선언만 되고 구현되지 않은 메서 |

  추상 클래스는 불안정하기 때문에 **단독적인 인스턴스를 만들 수 없고 클래스를 상속하고 구현 내용을 추가하는 방식**으로 사용합니다. 

```typescript
abstract class 추상클래스{
    abstract 추상메서드();
    abstract 추상멤버변수 : number;
    public 구현메소드() : void {
        공통적으로 사용할 로직
        로직에서 필요시 추상 메소드를 호출해 구현 클래스의 메서드가 호출되게 함
        this.추상메서드();
    }
}
```

 위의 코딩 방식은 코딩을 어느정도 해본 사람이 자주 쓰는 방법이다. 가령 리액트의 경우 부모 컴포넌트에서 자식 컴포넌트를 다룰 때 다음과 같은 방법을 사용할 수 있다.

{% hint style="info" %}
**abstract와 static 및 접근제한자**

abstract 키워드는 static 이나 접근 제한자\(private, public, protected\)와 함께 사용될 수 없습니다.   
abstract가 추가된 추상 메서드나 추상 멤버 변수는 자식 클래스에서 구현할 수 있도록 모두 public으로 선언되어야 합니다. 
{% endhint %}

 추상 클래스에 선언한 추상 메서드는 오버라이딩\(overriding\)해서 자식 클래스에서 반드시 구현해서 사용해야 합니다.

```typescript
class 자식클래스 extends 추상클래스{
    public 추상멤버변수 : string;
    public 구현메서드() : void {
        추상 메서드의 실제 구현 내
    }
}
```

