# 자바스크립트 Class\(ES+\)

## 자바스크립트의 Class

 ES+이전에는 자바스크립트에서는 class라는 키워드를 사용하지 않았습니다. 따라서 다른 언어를 사용하던 분이 자바스크립트의 객체에 대해 배울 때 prototype과 생성자 함수등에 대해서 배워야 했습니다.

 하지만 ES2015 이후 부터는 자바스크립트는 prototype을 내부적으로 사용하지만 class 키워드를 사용할 수 있도록 해주었습니다. 

 이를 바벨을 통해서 변환하면 불필요한 코드가 몇 개 추가되지만 기존의 class 키워드에 익숙한 개발자들은 이를 편리하게 사용할 수 있습니다.

```javascript
/*Before Code*/
var Dog = function(type){
    this.type = type || 'puppy';
};
// prototype으로 지정안해주면 static 으로 처리된다.
Dog.isDog = function(dog){
    return dog instanceof Dog;
};

Dog.prototype.bark = function() {
    alert("bow bow");
};

var JindoDog = function(type, firstName, lastName){
    Dog.apply(this, arguments);
    this.firsName = firstName;
    this.lastName = lastName;
};

JindoDog.prototype = Object.create(Dog.prototype);
JindoDog.prototype.constructor = JindoDog;
JindoDog.prototype.sayName = function(){
    alert(`${this.firstName} ${this.lastName}`);
};

var jindoDog = new JindoDog('jindoDog','stark','jeon');
```

 위와같은 코드를 ES+ 부터는 다음과 같이 만들 수 있습니다.

```javascript
class Dog{
    constructor(type = 'human'){
        this.type = type; 
    }
    
    static isDog(dog){
        return dog instanceof Dog;
    }
    bark(){
        alert("bow bow");
    }
}

class JindoDog extends Dog{
    constructor(type, firstName, lastName){
        super(type);
        this.firstName = firstName;
        this.lastName = lastName;
    }
    sayName(){
        suepr.bark();
        alert(`${this.firstName} ${this.lastName}`);
    }
}

const jindoDog = new JindoDog('jindo','stark','jeon');
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAD6C;&#xBD84;</th>
      <th style="text-align:left">&#xC124;&#xBA85;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">super</td>
      <td style="text-align:left">&#xBD80;&#xBAA8; &#xAC1D;&#xCCB4;&#xC5D0; &#xC811;&#xADFC;&#xD558;&#xB294;
        &#xBC29;&#xBC95;</td>
    </tr>
    <tr>
      <td style="text-align:left">instanceof</td>
      <td style="text-align:left">&#xBE44;&#xAD50; &#xD074;&#xB798;&#xC2A4;&#xAC00; &#xCC38;&#xC870; &#xBCC0;&#xC218;&#xAC00;
        &#xCC38;&#xC870;&#xD558;&#xB294; &#xD074;&#xB798;&#xC2A4;&#xC640; &#xB3D9;&#xC77C;&#xD55C;&#xC9C0;&#xB97C;
        &#xBB3C;&#xC5B4;&#xBCF4;&#xB294; &#xC5F0;&#xC0B0;&#xC790;&#xB85C; true,
        false&#xB97C; &#xBC18;&#xD658;&#xD55C;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">static</td>
      <td style="text-align:left">
        <p>&#xD074;&#xB798;&#xC2A4; &#xBCC0;&#xC218;&#xB85C;&#xC11C; &#xACF5;&#xC720;&#xC758;
          &#xC131;&#xACA9;&#xC744; &#xAC00;&#xC9C4;&#xB2E4;.</p>
        <p>&#xAC1D;&#xCCB4;&#xB97C; &#xC0DD;&#xC131;&#xD558;&#xC9C0; &#xC54A;&#xACE0;
          &#xD074;&#xB798;&#xC2A4;&#xC5D0;&#xC11C; &#xB9CC;&#xB4E0; &#xBCC0;&#xC218;&#xB97C;
          &#xC0AC;&#xC6A9;&#xD560; &#xC218; &#xC788;&#xB2E4;.</p>
        <p>&#xB370;&#xC774;&#xD130; &#xC601;&#xC5ED;&#xC5D0; &#xC18D;&#xD558;&#xAE30;
          &#xB54C;&#xBB38;&#xC5D0; &#xBA54;&#xBAA8;&#xB9AC;&#xC5D0; &#xD56D;&#xC0C1;
          &#xC0C1;&#xC8FC;&#xD574; &#xC788;&#xB2E4;.</p>
      </td>
    </tr>
  </tbody>
</table>