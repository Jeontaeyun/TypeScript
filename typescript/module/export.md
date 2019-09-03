# 외부 모듈 export

## 외부 모듈 Export

 타입스크립트는 ES2015의 모듈 시스템을 지원합니다. 이는 **import**와 **export 키워드**를 통해 모듈을 선언하고 호출합니다.

### 모듈 개별적 선언 및 호출

 함수와 인터페이스와 같은 단위별로 모듈화를 하기 위해서는 다음 방식을 사용합니다. 

```typescript
export interface Ironman{...};
export function hello(){};
```

 위와 같은 방식으로 모듈을 선언하고 아래와 같은 방식으로 모듈을 사용합니다. 

```typescript
import {Ironman, hello} from './export';
```

 단, 인터페이스는 컴파일 후에 사라집니다. 

### 모듈을 모아서 선언 및 호출

 모듈을 선언할 때 모든 모듈에 export를 붙이면 번거롭기 때문에 다음과 같이 한번에 모듈을 선언하고 호출할 수 있습니다.

```typescript
interface Ironman{...};
function hello() {...};
export {Ironman, hello };
```

 위와 같은 방식으로 모듈을 선언하고 아래와 같은 방식으로 모듈을 사용합니다. 

```typescript
import {Ironmna, hello} from './export';
```

