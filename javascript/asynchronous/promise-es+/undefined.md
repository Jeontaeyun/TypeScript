# 프로미스 사용하는 두 가지 방법

## 프로미스를 사용하는 두 가지 방법

 비동기 처리 함수\(Async Function\) 3개가 있을 때 이것이 그 전 작업이 수행된 후 수행되어야 하는 작업일 때 다음과 같이 **콜백을 이용해서 처리**합니다. 

```javascript
const async01 = (param, callback) => { 
    // Business Logic
    callback(param*2);
};
const async02 = (param, callback) => { 
    // Business Logic
    callback(param*3);
};
const async01 = (param, callback) => { 
    // Business Logic
    callback(param*4);
};

async01(1, (result) => {
    async02(result, (result01) => {
        async03(result01, (result02) => {
            console.log(result02);     // 24
        });
    });
});

```

### new Promise 패턴 

 위와 같은 방식이 반복된다면 Callback Hell\(콜백 지옥\)이라는 문제에 도달할 수 있다. 따라서 Callback Hell을 해소하기 위해 Promise 객체를 사용하며 대표적으로 다음과 같다.

```javascript
const async01 = (param) => {
    return new Promise((resolve, reject) => {
    //Business Logic
    resolve(param*2)
    });
}
const async02 = (param) => {
    return new Promise((resolve, reject) => {
    //Business Logic
    resolve(param*3)
    });
}
const async03 = (param) => {
    return new Promise((resolve, reject) => {
    //Business Logic
    resolve(param*4)
    });
}
async01
    .then(async02)
    .then(async03)
    .then(result => {
        console.log(result);    //24
    });
```

 위와 같이 구현 하면 **함수 선언 코드가 좀 길어지지만 함수 사용 부분은 좀 더 명확해집니다**.

### Promise.resolve\(function\(\)\) 패턴

```javascript
const async01 = (param) => {
    return Promise.resolve(param*2);
}
const async02 = (param) => {
    return Promise.resolve(param*3);
}
const async03 = (param) => {
    return Promise.resolve(param*4);
}

async01(1)
    .then(async02)
    .then(async03)
    .then((result) => {
        console.log(result);
    });
```

위와 같이 지정해주면 Promise 객체를 반환해주며 좀 더 깔끔하게 사용할 수 있습니다. 만약 reject를 처리하고 싶을 때는 다음과 같이 반환해주면 됩니다.

```javascript
return Promise.reject(err);
```

{% hint style="info" %}
프로미스의 then\(\)안에서나 async 함수에서 then\(\)안에서 return을 하면 Promise 객체로 다시 반환됩니다. 

에러는 throw new Error\(\)로 생성할 수 있습니다. 
{% endhint %}

