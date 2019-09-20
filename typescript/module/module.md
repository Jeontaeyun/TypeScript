# 모듈이란?

## 모듈 Module

 **모듈\(Module\)은 독립 가능한 기능의 단위**입니다. 프로그램은 여러 모듈로 구성돼 있고, 모듈을 결합해 하나의 프로그램을 만듭니다. 모듈을 사용하면 다음과 같은 장점이 있습니다.

* **유지 보수의 용이성**

  * 자주 사용하는 공통 기능을 모듈로 정의해 사용하면 애플리케이션의 전체적인 수정 없이 모듈의 수정이나 교체만으로도 코드를 효과적으로 수정할 수 있다.

  \*\*\*\*

* **전역 스코프 오염\(Global Scope Pollution\) 방지**

  * 전역 스코프는 전역 이름 공간\(Global Namespace\)를 가지므로 변수 이름이나 함수 이름을 중복 선언할 수 없는데, 이를 방지

* **재사용성\(Reusability\)** **향상**

* **모듈 단위 테스트가 가능해 에러 발생 확률 감소**

### 모듈러 프로그래밍

 **모듈러 프로그래밍\(Modular Programming\)**은 프로그램의 설계 기술로 모듈의 분리와 모듈의 손쉬운 교체에 관심이 있습니다. 모듈러 프로그래밍 방식으로 프로그램을 잘 구축하기 위해서는 **상호 교환 가능한 모듈\(Interchangeable Modules\)을 정의**할 수 있어야 합니다.

### 타입 스크립트 내부 모듈 \| 네임스페이스

 타입스크립트의 모듈은 내부 모듈과 외부 모듈로 나뉩니다. 내부 모듈은 **네임스페이스**를 의미합니다. 네임스페이스는 여러 파일에 걸쳐 하나의 이름 공간을 공유합니다.

네임스페이스마다 이름 공간을 두기 때문에 이름이 같은 모듈이더라도 네임스페이스가 다르면 이름 충돌이 발생하지 않습니다.

{% hint style="info" %}
**네임스페이스**   
  
타입스크립트에서는 같은 네임스페이스의 이름 공간이라면 파일 B가 파일 A에 선언된 모듈을 참조\(Reference\)할 수 있는데 참조할 때는 별도의 참조문을 선언하지 않아도 됩니다. 
{% endhint %}

 네임스페이스는 namespace 키워드를 통해서 선언할 수 있습니다. 

```typescript
namespace Stark {
    ...
}
```

#### 한 파일에 여러 네임스페이스 선언

 한 파일에 여러 네임스페이스를 선언하면 네임스페이스마다 이름 공간이 구분돼 있으므로 서로의 이름 공간에 접근하려면 모듈을 export로 선언해야 합니다. 

```typescript
namespace Stark {
    export const name = "Stark";
    export function getName(){
        return Taeyun.name;
    }
}

namespace Taeyun{
    export const name = "Taeyun";
}
console.log(Stark.name);            // Stark
console.log(Stark.getName());       // Taeyun
```

#### 네임스페이스 하나를 여러 파일에 선언

 네임스페이스를 이용하면 여러 파일에 걸쳐 하나의 네임스페이스의 이름 공간을 공유할 수 있습니다. 

즉, 네임스페이스의 이름만 같다면 컴파일 시에 **명시적으로 참조 경로를 추가하지 않아도 타입스크립트 컴파일러가 알아서 네임스페이스 간의 참조 관계를 고려해 컴파일** 합니다.

단, 프로젝트 단위의 컴파일이 아니니 특정 파일만 컴파일 하고 싶을 때는 참조 경로를 다음과 같이 명시해주어야 합니다.

```typescript
/// <reference path ='people.ts'/>

namespace People{
    ...
}
```

 **참조 경로\(Reference Path\)**를 선언하기 위해서 **트리플 슬래시\(///\)**를 사용 합니다. 

#### 네임스페이스 모듈

 네임스페이스는 export를 이용해 모듈로 선언할 수 있습니다. 모듈로 선언된 네임스페이스는 import문을 이용해 JS로 컴파일 된 뒤에 명시적으로 모듈 호출\(Import문, Require 함수 등\)을 할 수 있습니다. 

```typescript
export namespace People {...}
```

#### 네임스페이스 이름 확장

 네임스페이스 이름은 점\(.\)을 이용해 확장 가능합니다. 이를 통해 네임스페이스 간의 이름 계층을 만들 수 있습니다. 

```typescript
export namespace People{...}
export namespace People.Greating{...}
export namespace People.Growing{...}
```

  단, 이름 공간은 논리적인 계층을 따르며 선언되는 것이 좋으며 불러올 때\(임포트\)는 네임스페이스의 최상위 이름만을 이용해야 합니다.

```typescript
import {People} from './namespace';
```

#### 브라우저에서 네임스페이스 모듈 확장 



