# 중급 2강. 생성자 함수 (Constructor function)
## 객체 리터럴 (Object literal)
- 객체는 객체명을 선언하고 중괄호로 묶어 프로퍼티(키 : 값)의 형태로 쉼표로 구분하여 나열한다.
```js
let user = {
  name : 'Mike',
  age : 30,
}
```
---
## 생성자 함수 (Constructor function)
- 다량의 동일한 양식의 객체 리터럴을 만들어낼 때 사용하는 함수이다.
- 함수명의 첫글자는 대문자로 한다.
- 생성자 함수를 호출하여 새로운 객체를 만들 때는, 생성자 함수 앞에 `new` 연산자를 붙인다.
  ```js
  function User(name, age) {  
    this.name = name;
    this.age = age;
  }
  let user1 = new User('Mike', 30); // 생성자 함수를 호출할 때 앞에 new 연산자를 붙인다.
  let user2 = new User('Jane', 22);
  let user3 = new User('Tom', 17);
  ```
- 호출 과정
  ```js
  function User(name, age) {
  //this = {};  -- 먼저 this라는 객체를 생성한다.
    this.name = name; 
    this.age = age; // this 객체에 프로퍼티를 넣는다.
  //return this;  -- 객체 this를 반환한다.
  }
  new User('Mike', 21); // new를 함수명 앞에 붙이면 위의 알고리즘대로 실행이된다.
  ```
  

