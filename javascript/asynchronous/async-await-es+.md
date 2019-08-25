# async와 await \(ES+\)

## Async와 Await

 콜백을 통해서 비동기 처리를 할 수 있게 된 후 지나친 콜백으로 인해 발생한 콜백지옥을 해결하기 위해 프로미스 객체를 도입한 것을 확인했습니다.

 하지만 프로미스 객체를 사용하더라도 then, catch 등 프로미스 객체를 이용할 때 코드가 여전히 복잡하다는 생각이 들 수 있습니다. ECMA에서는 비동기 코드를 동기식으로 표현하는 **async / await** 문법을 도입했습니다.

{% hint style="info" %}
**비동기 호출을 동기화** 

비동기 호출이 이루어지면 보통 응답 시점을 무시하고 작업이 응답되기 전에 다음 작업을 진행하므로 전체 코드의 실행 시간은 짧습니다. 

하지만 때론, 비동기 호출 시 순차적으로 이뤄져야할 상황이 있습니다. 이는 하나의 비동기 함수의 호출 결과가 다른 비동기 함수의 호출 결과에 영향을 미치는 경우가 그렇다.

이럴 때 Async Await 키워드를 이용한다. 
{% endhint %}

### Async \| Await 사용

```javascript
const findPost = async() => {
    try{
        (...)
        let post = await Posts.findOne({id: id}).exec();
        (...)
    }
    catch(e){
        console.error(e);
    }
}
```

  async 함수는 Promise가 없으면 의미가 없습니다. 또한 await 키워드는 async 로 선언된 함수 내부에서만 사용할 수 있습니다. **await함수는 Promise를 받아 처리하는 키워드입니다.**

 단, **await 키워드는 반드시 async함수 바로 안에서만 쓰여야 한다는 점입니다. async 함수 안에 또 다른 일반함수가 있고 그 안에 await이 있다면 안됩니다.**

```javascript
const test = async() => {
    const asyncTest = () => {
        await Promise.resolve(true);
    }
}
// 위의 코드는 async 함수 바로 안이 아니라서 에러가 발생합니다.
```

### Async \| Await 예외 처리

 프로미스 객체에서는 catch\(\)로 에러를 처리했다면, async 함수에서는 try-catch 문법을 사용하여 예외를 처리합니다.

```javascript
const asyncTest = async()=>{
    try{
        (에러 없을 때 처리 then 부분)
    }
    catch(e){
        (에러 발생시 처리 catch 부분)
    }
}
```

### Async \| Await 반환값

 async함수는 return 또는 throw값이 담긴 **Promise객체를 리턴**합니다. 따라서 이를 받아 then또는 catch처리를 할 수도 있습니다.

```javascript
const testPromise = async() => {
    return 'zero';
}
testPromise().then((res)=>{
    console.log(res);             // 'zero'
});
```

### Promise.all과 for await of

 async함수 안에 여러 await이 있을 때 앞의 await이 완료된 후에 뒤의 await이 실행됩니다. 하지만 이를 모두 동시에 실행하고 싶을 때가 생길 수 있습니다. 이때는 다음과 같은 방식으로 해결할 수 있습니다.

```javascript
const result = async() => {
    await Promise.all([프로미스...]);
}
```

 또한 ES2018\(ES9\)부터는 for await of 문법이 추가되어 await Promise.all\(\)을 대체하였습니다. ES2018부터 async 문법을 Generator과 for of 문에서도 사용가능하게 되었습니다.

```javascript
async() => {
const promises = ['1000', '2000', '3000'].map((timer)=>{
    new Promise((res,rej)=>{
        setTimeout(()=> res(timer), timer);
    });
    // 1초, 2초, 3초 이후
});

for await (const result of promises){
    console.log(result);
}
}    
```

