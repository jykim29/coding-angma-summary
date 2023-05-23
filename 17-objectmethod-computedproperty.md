# 중급 3강. 객체 메소드(Object method)와 계산된 프로퍼티(Computed property)
## 객체 메소드 (Object method)
- `Object.assign()` : 객체 복제
  ```js
  // 기본형
  const newUser = Object.assign(초기값, 덮어쓸 객체1, 덮어쓸 객체2, ...);
  ```
  ```js
  const newUser = Object.assign({}, user);  // user의 객체 내용을 초기값 빈객체({})인 newUser에게 덮어씌운다.
  ```

- `Object.keys()` : 프로퍼티 키를 배열로 반환
  ```js
  const user = {
    name : 'Mike',
    age : 30,
    gender : 'Male',
  }
  Object.keys(user);  // ['name', 'age', 'gender'] 로 반환
  ```

- `Object.values()` : 프로퍼티 값을 배열로 반환
  ```js
  const user = {
    name : 'Mike',
    age : 30,
    gender : 'Male',
  }
  Object.values(user);  // ['Mike', 30, 'Male'] 로 반환
  ```

- `Object.entries()` : 프로퍼티 키와 값을 쌍으로 배열로 반환
  ```js
  const user = {
    name : 'Mike',
    age : 30,
    gender : 'Male',
  }
  Object.entries(user);  // [ ['name', 'Mike'], ['age', 30], ['gender', 'Male'] ] 로 반환
  ```

- `Object.fromEntries()` : entries와 반대개념. 키, 값 쌍으로 된 배열을 객체로 반환
  ```js
  const arr = [
    ['name', 'Mike'],
    ['age', 30],
    ['gender', 'Male'],
  ]
  Object.entries(arr);  // {name : 'Mike', age : 30, gender : 'Male'} 로 반환
  ```
  
---
## 계산된 프로퍼티 (Computed property)
- 사용자가 입력한 프로퍼티 키 대신에 `[변수]` 형태로 넣을 수 있다. 이것을 **계산된 프로퍼티 (Computed property)** 라고 한다.
  ```js
  let a = 'age';
  const user = {
    name : 'Mike',
    [a] : 30, // 프로퍼티 키를 변수 a로 놓았다.
  }
  ```
