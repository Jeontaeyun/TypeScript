# 테스트 툴

## 테스트 툴

### TDD \| Test Driven Development

 프로그래머의 개발 방법 패러다임의 하나로 테스트로 부터 프로그래밍을 시작하는 개발 방식을 말한다. 

개발자는 먼저 요구사항을 검증하는 자동화된 테스트 케이스를 작성하고, 테스트 케이스를 통과하기 위한 최소한의 코드를 작성한다.

 마지막으로 작성한 코드를 표준에 맞도록 리팩토링하는 방식으로 개발을 진행한다. 

### JEST \| 자바스크립트 테스트 프레임 워크

 단순성에 초점을 둔 페이스북에서 만든 **자바스크립트 테스트 프레임 워크**로, Babel, TypeScript, Node.js, React.js, Angular 및 Vue.js를 사용하는 프로젝트에서 자주 사용됩니다. 

 JEST 이전에는 자바스크립트 코드를 테스트 하기 위해 다양한 테스팅 라이브러리를 조합해서 사용해야 했습니다. 하지만, JEST는 라이브러리 하나에 Test Runner, Test Matcher 그리고 Test MOck 프레임워크까진 제공해주는 **All in one 테스트 프레임워크**입니다.

#### 설치 방법

```bash
$npm install --save -dev jest
```

```javascript
//pakcage.json

{
    ...
    "scripts" : {
        "jest" : "jest" 
    }
}

```

#### 워크 플로우 

1.  시나리오 작성
   * 스토리는 당장 개발할 것과 추후에 개발할 것을 정의하고 이를 이후에 추가하면 된다. 
2.  테스트 코드 작성
3.  기능 구현
4.  리팩토링 

 위의 과정을 반복적으로 가지며 **중복되는 코드를 제거**하고, **기능을 분리**한다. 

#### 테스트 패턴

```javascript
//test.js

test('테스트 설명', () => {
    expect('검증 대상').toXXX('기대 결과')
});
```

 이 때 toXXX부분을 Matcher라고 하며 JEST에선 거의 대부분의 경우에 대한 Matcher 함수를 제공합니다.

| Matcher 함수 | 설명  |
| :--- | :--- |
| **toBe\(\)** | 숫자나 문자와 같이 Primitive 자료형을 비교하는 Matcher 함수 |
| **toEqual\(\)** | 객체 자료형 비교할 때 사용하는 Matcher 함수 |
| **toBeTruthy\(\)** | 자바스크립트 언어에서 true로 반환하는 자료형을 비교하여 테스트하는 Matcher 함수  |
| **toBeFalsy\(\)** | 자바스크립트 언어에서 false로 반환하는 자료형을 비교하여 테스트하는 Matcher 함수 |
| **toHaveLength\(\)** | 배열의 길이를 체크하는 Matcher 함수 |
| **toContain\(\)** | 배열 안에 특정 원소가 들어있는지 테스트 하는 Matcher 함수  |
| **toMatch\(\)**  | 정규식 기반의 문자열을 테스트 하기 위한 Matcher 함수  |
| **toThrow\(\)** | 예외 발생 여부를 테스트 해야할 때 사용하는 Matcher 함수  |

{% hint style="info" %}
**test.js 파일과 \_\_test\_\_디렉토리**

JEST는 기본적으로 test.js로 끝나거나, \_\_test\_\_ 디렉토리 안에 있는 파일들을 모두 테스트 파일로 인식합니다.

특정 테스트 파일만 실행하고 싶을 때 스크립트 명령에 따로 파일명이나 경로를 명시해주어야 합니다.
{% endhint %}

### 단위 테스트 \| Unit Test

#### 단위 테스트 규칙

* 독립적\(Independent\)인 환경이어야 한다. 

  * 각 테스트가 서로에게 영향을 미치면 안된다.

* 테스트가 격리\(Isolation\)되어야 한다.

  * Ajax, LocalStorage, UI Event 등 테스트 대상이 의존하는 것을 다른 것으로 대체해야한다. 이렇게 대체하는 것을 테스트 더블이라고 한다. 

* given, when, then 단계에 따라 테스트 코드를 작성해야한다

* 단위 테스트의 목적은 단위별로 정확한 동작을 하는 기능을 조합하여 신뢰성 높은 개발을 하기 위함이다

  * 실제 개발환경에서 테스트를 진행할 경우 파일의 크기가 커서 다시 디버깅하고 빌드하는데 시간이 오래걸린다. 따라서 작은 단위로 테스트를 진행해 시간 자원을 절약할 수 있다. 

#### 단위 테스트 스토리와 시나리오 작성법

```text
Story. 사용자는 Modal을 생성할 수 있다.
    senario
        given: 설정없이
        when: Modal을 생성하면
        then: defualt 속성을 가진 Modal이 생성된다.
Story. 사용자는 Modal 창을 열 수 있다.
    senario
        given: 모달이 꺼졌을 때
        when: 모달 버튼을 누르면,
        then: 모달 창이 나타난다
Story. 사용자는 Modal 창을 끌 수 있다.
    senario
        given: 모달이 켜졌을 때
        when: 모달 버튼을 누르면,
        then: 모달 창이 나타난다
```

