# 11강. 함수 표현식, 화살표 함수(arrow function)
## 함수 표현식
- 기본형
  ```js
  let sayHello = function() {
    console.log('Hello');
  }
  sayHello();
  ```
---
## 함수 선언문과 함수 표현식
- 공통점 : 사용방식과 실행하는 방식 모두 동일하다.
- 차이점 : 호출할 수 있는 타이밍이 서로 다르다.
  
  - 함수 선언문 : 함수 위에서든 밑에서든 **어디서든 호출할 수 있다.**
  ```js
  sayHello();

  function sayHello() {
    console.log('Hello');
  }

  sayHello();
  ```
    그런데 자바스크립트는 위에서부터 아래로 한줄씩 차례대로 코드를 실행하고 그 줄의 결과를 즉시 반환하는 <u>인터프리터 언어(Interpreted Language)</u>이다. 어떻게 위와 같은 일이 가능할까?  
    다음 단락 '함수 호이스팅' 에서 그 이유에 대해 알아보도록 하겠다.
    - 함수 표현식 : 해당 함수 코드에 도달해서야 비로소 함수 생성
    ```js 
    // ...
    // ...
    let sayHello = function() { // 이 코드에 도달해서야 함수 생성
      console.log('Hello');
    }
    // 함수 이후에서만 사용가능
    sayHello();
    ```
---
## 함수 호이스팅
![](images/11-1.png)
- 정의 : 자바스크립트의 인터프리터(Interpreter)가 코드를 컴파일(Compile)하는 과정에서, **그 코드에 선언된 함수들을 최상단으로 끌어올리는(hoisting) 것**을 말한다. 실제로 함수 코드가 위로 올라가는 것은 아니다.
---
## 함수 선언문 vs 함수 표현식
- 무엇을 쓰던 상관은 없지만 에러를 신경 쓰기 싫다면 함수 선언문을 사용하는 것이 더 편하다.
---
## 화살표 함수 (arrow function)
- 화살표 (=>) 를 이용하여 함수 표현식을 더 간결하게 표현할 수 있다.
- 화살표 함수의 다양한 형태
```js
// 함수 표현식
let showError = function() {
  console.log('Error!');
};

// 화살표 함수 
// 1. 인자와 return이 없는 경우
let showError = () => {
  console.log('Error!');
}

// 2. 인자와 return이 있는 경우
let add = (num1, num2) => {
  return num1 + num2;
}
// 여기서 함수코드가 return 한줄밖에 없다면, return을 생략하고 중괄호를 소괄호로 바꿀 수 있다. 그리고 이 소괄호마저 없앨 수 있다.
let add = (num1, num2) => (
  num1 + num2;
)
let add = (num1, num2) => num1 + num2;
```
