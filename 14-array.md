# 14강. 배열 (Array)
## 기본형
```js
let students = ['철수', '영희', '민수', '나리', '영호']
// 인덱스(index)  0       1       2       3       4
```
## 특징
- 배열은 문자형 뿐만 아니라 숫자, 객체, 함수 등도 포함 할 수 있다.
- length : `변수명.length` 로배열의 길이를 알 수 있다. `students.length'`는 5가 된다.
- push() : 배열 맨 끝에 요소를 추가한다.
  ```js
  let days = ['월', '화', '수'];
  days.push() = '목';
  console.log(days); // ['월', '화', '수', '목']
  ```
- pop() : 배열 맨 끝에 요소를 제거한다.
  ```js
  let days = ['월', '화', '수', '목'];
  days.pop();
  console.log(days); // ['월', '화', '수']
  ```
- unshift/shift : 배열 맨 앞에 요소를 제거/추가 한다. 여러요소를 한번에 추가 할 수 도 있다.
  ```js
  days.unshift('금', '토', '일');
  console.log(days); // ['금', '토', '일', '월', '화', '수']
  days.shift('일');
  console.log(days); // ['월', '화', '수']
  ```
---
## 반복문에서의 쓰임새
- 배열을 사용하는 가장 큰 이유 중의 하나는 반복을 위해서이다.
- 반복문 for
  ```js
  let days = ['월', '화', '수'];
  for(let index=0 ; index < days.length ; index++) {
    console.log(days[index]);
  }
  // 결과 : ['월', '화', '수']
  ```
- 반복문 for ~ of : 장점보다 단점이 많아서 권장하지 않는다.
  ```js
  let days = ['월', '화', '수'];
  for(let day of days){
    console.log(day);
  }
  // 결과 : ['월', '화', '수']
  ```