# 프로미스 \| Promise \(ES+\)

## 프로미스

 자바스크립트나 Node.js에서 자주 사용하는 콜백 패턴은 비동기적으로 작업을 하는 자바스크립트 언어에서 아주 유용하게 사용하는 패턴입니다. 하지만, 이러한 콜백을 여러번 사용해서 중첩한다면 어떻게 될까요?

```javascript
Post.findOne({...}, (err, post) =>{
    (...)
    post.save((err)=>{
        (...)
        post.findOne({...}, (err)=>{
            (...)
        });
    });
});
```

 이 처럼 코드각 중첩될 때 마다 코드가 안으로 들어가고 중괄호{}와 소괄호\(\)가 반복되는 것을 확인할 수 있습니다. 이런 코드가 기능적으로는 문제가 없지만 프로그래밍이 사람이 하는 일이다 보니 중괄호를 잘 못 써 프로그램이 오류가 나거나 오타가 발생하기도 합니다. 또한, 이런 콜백의 중첩이 반복되면 가독성이 떨어져 같이 협업하는 동료 개발자들의 협업 혹은 유지 보수를 어렵게 만듭니다.

 이런 콜백의 지옥\(Call Back Hell\)에서 우리를 구원해주기 위해 ES2015\(ES6\)부터는 Promise 패턴을 공식적으로 지원하기 시작했습니다.

### 프로미스 객체 \| Promise Object 

 프로미스는 비동기 작업을 도와주는 객체입니다. `new Promise((resolve, reject)=>{...});`를 통해서 프로미스 객체를 생성할 수 있으며 then, catch를 통해서 에러처리를 담당합니다. 아래 코드를 통해서 프로미스 객체의 사용법을 대략적으로 파악할 수 있습니다.

```javascript
/*프로미스 객체 생성*/
const promise = new Promise((resolve, reject) => {
    try{
        (...비동기 작업)
        resolve(결과값);
    }
    catch(e){
        reject(e);
    }
});

/*프로미스 객체 사용*/
promise.then((result) => {...}).catch((e) => {console.log(e)})

```

 then과 catch에 들어가는 값은 resolve\(결과값\)의 결과값이 then의 result로 넘어가고, reject\(e\)의 에러가 catch의 에러 값으로 넘어갑니다.

### 프로미스 응용 \| Promise.all

 여러 프로미스 객체들을 한번에 모아서 처리할 수 있는 메소드입니다. 이 메소드는 프로미스가 성공하면 then, 하나라도 실패하면 catch로 연결됩니다.

```javascript
/*Promise.all의 예시*/

// new Promise 없이 성공한 Promise 객체를 만드는 방법
let p1 = Promise.resolve('zero'); 
let p2 = Promise.resolve('nero');

// new Promise 없이 실패한 Promise 객체를 만드는 방법
let p3 = Promise.reject('error'); 

// 보통 Promise.all()안에는 배열의 형태로 넣어준다.
Promise.all([p1, p2, p3]).then((result) => {
  console.log(result); 
}).catch((err) => {
  console.error(err)
});
```

### 프로미스 finally \| ES2018

 ES2018 이후 부터는 Promise에 then과 catch 외에도 **finally**가 추가되어 Promise의 성공, 실패 여부와 상관없이 무조건 실행되는 메서드를 추가할 수 있습니다.

```javascript
Promise.resolve("hello World")
    .then((msg) => Promise.resolve(msg))
    .finally(()=>console.log("finally!")
    .then((msg)=> console.log(msg));

// finally! World가 나온다.
```

ES2018 설명을 보면 finally에서 반환\(return\)하는 프로미스는 resolve값을 바꿀 수 없고 reject값만 바꿀 수 있습니다.

