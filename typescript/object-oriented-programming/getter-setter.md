# 타입스크립트 Getter 와 Setter

## 타입스크립트 Getter와 Setter

 타입스크립트는 클래스 내에 **get\(접근자\)과 set\(설정자\) 키워드를 이용해 getter와 setter를 선언**할 수 있습니다.

```typescript
class People {
    name: string;
    age : number;
}
const people = new People();
people.name = "Stark";            // 속성값 설정
console.log(people.name);         // 속성값 읽기 
```

 만약 **값을 설정하거나, 읽을 때 특별한 로직을 추가하고 싶다면 get/set 키워드로 접근자와 설정자를 추가해 줄 수 있습니다**.

```typescript
class People {
    private name : string;
    private age : number;
    get getName(): string {
        return this.name;
    }
    set setName(name:string){
        if(name.indexOf("man") !== 0){
            this.name = name;
        }
    }
}
const people = new People();
people.setName("Stark");
console.log(people.getName());        // Stark 
```

 위와 같은 특징을 이용해 특정 객체의 값을 추가하는 로직을 만들 수 있어 유용합니다. 

