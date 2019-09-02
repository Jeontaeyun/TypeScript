# 객체 지향 다형성

## 클래스와 인터페이스 기반의 다형성

 **다형성\(Polymorphism\)**은 여러 타입을 받아들임으로써 여러 형태를 가지는 것을 의미합니다. 타입스크립트는 다음 3가지의 다형성의 대표적인 예를 가집니다. 

* 클래스의 다형성

* 인터페이스의 다형성

* 매개 변수의 다형성

### 클래스의 다형성

 부모 클래스 A를 자식 클래스 B에 상속할 때 부모 클래스 A가 변수의 타입으로 자식 클래스의 객체에 할당 될 수 있습니다. 이때, 부모 클래스 A는 부모 클래스 A를 상속하는 어떤 자식 클래스의 타입이라도 받아들일 수 있는 다형 타입\(Polymorphic Type\)이 되고 다형성을 띠게 됩니다. 

```typescript
class People{
    ...
}
class Developer extends People{
    ...
}
const Stark : People = new Developer();
```

 위와 같이 People 클래스의 자식 클래스인 Developer객체를 People타입의 변수에 할당하면 자동으로 **업캐스팅\(Upcasting\)**되어 다형성이 생깁니다.



