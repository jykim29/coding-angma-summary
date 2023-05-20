# 12강. 객체 (Object)
## 기본형
- 객체는 중괄호 안에 키(key)와 값(value)를 갖는 프로퍼티(property)로 구성되어있으며 여러개의 프로퍼티를 쉼표(,)로 구분한다.
  ```js
  const superman = {
    name : 'clark', // name : key, 'clark' : value 
    age : 33, // 마지막 프로퍼티는 쉼표가 없어도 되지만 이동과 수정의 편의를 위해 붙여준다.
  }
  ```
---
## 객체의 접근, 추가, 삭제
- 접근 : 접근할 객체명 뒤에 점(.)이나 대괄호( [ ] )를 사용하여 접근한다.
  ```js
  superman.name // 'clark'
  superman['age'] // 33
  ```
- 추가 : 객체명 뒤에 점(.)이나 대괄호( [ ] )를 사용하여 프로퍼티를 추가한다.
  ```js
  superman.gender = 'male';
  superman['hairColor'] = 'black'
  ```
- 삭제 : `delete` 키워드를 사용하여 삭제하고 싶은 프로퍼티를 적는다.
  ```js
  delete superman.hairColor;
  ```
---
## 단축 프로퍼티
- 'key : value' 프로퍼티 대신 변수명을 사용하여 프로퍼티를 단축시킬 수 있다.
  ```js
  const name = 'clark';
  const age = 33;
  const superman = {
    name, 
    age,  // 변수명을 적는다.
    gender : 'male',
  }
  ```
---
## 프로퍼티 존재 여부 확인
  ```js
  const superman = {
    name : 'clark',
    age : 33,
  }

  superman.birthDay;  // 없는 프로퍼티는 undefined 출력
  'birthDay' in superman; // 'birthDay'의 존재 여부 false 출력
  'age' in superman; // 'age'의 존재 여부 true 출력
  ```
---
## for ~ in 반복문
- 방식 : 객체에 있는 프로퍼티 수 만큼 반복한다. 한번 반복할 때마다 다음 프로퍼티로 넘어간다.
  ```js
  for(let 프로퍼티 in 객체명) {
    console.log(프로퍼티);  // 객체의 프로퍼티명 출력
    console.log(객체명[프로퍼티]);  // 객체 프로퍼티의 값 출력
  }
  ```
## 객체를 반환하는 함수
- 함수의 return문에 중괄호를 넣고 그 사이에 프로퍼티들을 나열해서 객체를 반환할 수 있다.
  ```js
  function makeObject(name, age) {
    return {
      name : name,
      age : age,    
      hobby : 'football',
    }
  }
  ```
---
## 응용 예제코드
- `isAdult` 함수에 객체인자를 받아서 성인인지 판단하는 코드
  ```js
  function isAdult(user) {
    if (user.age < 20) {
      return false; // age 프로퍼티가 20 미만이면 false 반환
    }
    else if (user.age >= 20) {
      return true;  // age 프로퍼티가 20 이상이면 true 반환
    }
    return "Can't find 'age' property.";  // undefined일 경우 메세지 반환
  }

  const guest1 = {
    name : 'Mike',
    age : 18,
    hobby : 'game',
  }
  const guest2 = {
    name : 'Sora',
    // age 프로퍼티가 없으므로 guest2.age는 undefined가 된다.
    hobby : 'sleep',
  }
  console.log(isAdult(guest1)); // 결과 : false
  console.log(isAdult(guest2)); // 결과 : "Can't find 'age' property."
  ```
- for ~ in 반복문을 통하여 객체의 프로퍼티와 값 출력
  ```js
  const user = {
    name : 'John',
    age : 22,
    job : 'Student',
  }
  
  for(x in user) {
    console.log(x+" "+user[x]); // 각 프로퍼티마다 반복하여 값을 출력
  }
  /* 결과 : name John
            age 22
            job Student  */
  ```
    - 객체 접근 시, `user.x` 로 접근이 불가능한 이유는 `x`가 프로퍼티를 <u>문자열</u>로 받아오기 때문이다.  
    - 예를 들어 `x`가 `name` 프로퍼티를 받아올 경우 `"name"`이란 문자열로 받게 되며, 곧 `user."name"`이란 뜻이 되므로 **오류가 발생한다.**