# 중급 1강. 변수, 호이스팅, TDZ(Temporal Dead Zone)
## 변수 (`var`, `let`, `const`)
- `let`과 `const`는 ES6부터 새로 나온 개념이다.
- `var`
  1. 한번 선언된 변수는 다시 선언할 수 있다.
      ```js
      var name = 'Mike';
      console.log(name);  // 'Mike'
      var name = 'Jane';
      console.log(name);  // 'Jane'
      ```
  2. 선언하기 전에 사용할 수 있다.
      ```js
      /*
      var name; // 이렇게 동작하기 때문에 선언하기 전에는 undefined가 된다. */ 
      console.log(name);  // undefined
      var name = 'Mike';
      ```
      - 호이스팅(Hoisting) : `var`로 선언한 모든 변수는 코드가 실제로 위로 이동하진 않지만, 코드가 최상위로 끌어올려진 것 처럼 동작한다. 이를 **호이스팅(Hoisting)** 이라고 한다.  
      그런데 'Mike'가 출력되지 않고 undefined가 출력된 이유는 **선언은 호이스팅 되지만 할당값은 호이스팅 되지 않기 때문이다.** 
- `let`
  1. 한번 선언된 변수를 다시 선언할 수 없다.
      ```js
      let name = 'Mike';
      console.log(name);  // 'Mike'
      let name = 'Jane';
      console.log(name);  // 'error: name has already been declared.
      ```
  2. <u>TDZ(Temporal Dead Zone)</u>에 영향을 받아 할당받기 전에는 사용할 수 없다.
      ```js
      console.log(name);  // error발생: let이 할당받기 이전인 TDZ영역에서 변수를 사용할 수 없다.
      let name = 'Mike';
      console.log(name);  
      ```
  3. 블록스코프 단위로 유효하기 때문에 호이스팅도 블록스코프 단위로 일어난다.
      ```js
      let age = 30; // 블록 밖인 전역 변수이므로 블록 내, 외 모든 스코프에서 유효하다.
      function showAge(){
        console.(age);  // 밑에 let이 할당받기 이전인 TDZ영역에서 변수를 사용할 수 없다.
        let age = 20; // let 변수형은 블록스코프 단위에서만 유효하므로 여기서 age는 showAge함수 블록 내에서만 유효하다.
      }
      showAge();
      ```
---
## 변수의 생성과정
- 변수는 생성될 때 3개의 단계를 거친다.
  1. 선언 단계
  2. 초기화 단계
  3. 할당 단계   
- `var` 는 선언과 초기화 단계가 동시에 이루어진다.
  1. 선언 및 초기화 단계 *(초기화단계 : undefined를 할당하는 단계)*
  2. 할당 단계
- `let`은 선언과 초기화 단계가 따로 이루어진다.
  1. 선언단계
  2. 초기화 단계
  3. 할당 단계
- `const`는 선언과 초기화와 할당 단계가 동시에 이루어져야 한다.
  1. 선언 + 초기화 + 할당 단계
---
## 변수의 스코프
- `var` : 함수 스코프 (function-scoped), 함수 내에서 선언된 변수는 함수 밖에서 사용 될 수 없다.
- `let`, `const` : 블록 스코프 (block-scoped), 중괄호({ })로 감싸진 코드블록 안에서 선언된 변수는 그 안에서만 사용될 수 있다.