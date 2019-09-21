# 타입스크립트 제네릭 클래스와 인터페이스

## 제너릭 클래스와 인터페이스

 자료구조나 알고리즘은 타입에 의존적이면 범용으로 사용할 수 없다. **범용으로 사용할 목적의 자료구조나 알고리즘이 있다면 다양한 타입에 댕으하도록 제너릭을 적용해야 한다**. 

### 제너릭 클래스 \| Generic Class

 제너릭 클래스\(Generic Class\)는 외부로부터 타입을 받아들여 클래스 내부에 이를 적용할 수 있는 클래스입니다. 다음과 같은 형태로 선언합니다.y

```typescript
class 클래스명<T>{
    getValue(el: Array<T>, idx: number): T{
        return el[idx];
    }
}
```

 위와 같은 방식으로 다음과 같은 배열 변환기 클래스를 구현할 수 있습니다.

```typescript
class ArrayConvertor<T>{
    el: Array<T>;
    constructor(el: Array<T>){
        this.el = el;
    }
    array2string(): string{
        let text = "";
        for(let i = 0 ; i < this.el.length ; i++){
            if(i>0){
                text+="";
            }
            text += this.el[i].toString();
        }
        return text;
    }
    getValue(el:Array<T>, idx:number){
        return el[idx];
    }
}
let arr = [1,2,3,4,5];
let numConvertor = new ArrayConvertor<number>(arr);
console.log(numConvertor.array2string());
console.log(numConvertor.getValue(arr, 0));
```

### 타입 매개변수에 인터페이스를 상속

 제너릭 클래스에 전달된 매개변수가 클래스이고 타입 매개변수일 때 코드 어시스트를 받지 못할 때가 있습니다. 이는 타입 매개변수 &lt;T&gt;에 타입이 없기 때문입니다. 이를 해결하기 위해서는 다음과 같이 **&lt;T extends 인터페이스&gt;처럼 클래스에 대한 인터페이스를 상속**해주면 됩니다. 

만약 타입 매개변수 T가 특정 인터페이스로 제약될 필요가 있다면 일반 클래스를 제너릭 클래스로 변환해야 합니다. 

```typescript
interface IName{
    name: string;
}

class Profile2 implements IName{
    name: string = "stark";
}

class Accesor2<T extends IName>{
    getKey(obj: T){
        return obj.name;
    }
}
```

 메서드 단위로 제너릭을 적용하는 것은 특정 메서드에만 타입 인수를 전달할 수 있으므로 타입의 재활용성이 다소 떨어집니다. 

그런데 클래스 단위로 제너릭을 적용하면 클래스 내에 존재하는 **불특정 메서드에 대해 일괄적으로 제너릭 메서드로 선언할 수 있어서 더 편리**합니다. 

