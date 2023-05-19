# 2강 자료형
## 문자형 string : ""(double quote), ''(single quote), `(backtick) 사용
- `""` 안에 `"` 사용불가능 대신 `'`을 사용, 만약 사용하려면 앞에 `\`을 붙인다.
- 문자열 표현 방법
```javascript
 const message1 = "I'm a boy."; 
 // double quote 안에 single quote 사용 가능
 ```
```javascript 
const message2 = 'I\'m a boy.'; 
// single quote 안에 single quote 사용 불가능 → 앞에 \붙임.
```
```javascript
const message3 = `My name is ${name}`; 
// 변수와 함께 쓸 경우 backtick 사용
```
  - backtick 문자열 안에서 변수 표기법 : `${변수명}`
---
## 숫자형 number
- 숫자형은 감싸는 기호 없이 사용
- 사칙연산과 나머지연산이 가능
- 숫자를 0으로 나눌 경우 → `Infinity` 출력
- 문자형을 숫자로 나눌 경우 → `NaN`(Not a Number) 출력
---
## 논리형 boolean
- `true`인지 `false`인지 표현
---
## null과 undefined
- `null`은 존재하지 않는다는 의미
- `undefined`는 할당되지 않았다는 의미
---
## typeof 연산자
- 자료형을 알려주는 연산자
- 타인이 적은 코드나 api를 이용하여 받은 코드를 분석할 때 사용 
- `typeof null;`은 `object`(객체형)이다. 하지만 `null`은 객체가 아니다. → 자바스크립트 초기버전의 오류, 호환성 위해 수정하지 않음
--- 
## 몇가지 팁
- 문자형과 문자형을 합치면 하나의 문자형이 된다. 
```javascript
const name = "Kim";
const a = "나는 ";
const b = " 입니다.";
console.log(a + name + b); → "나는 Kim 입니다."
```
- 숫자형과 문자형을 합치면 하나의 문자형이 된다.
```javascript
const age = "30살";
const a = "나는 ";
const b = " 입니다.";
console.log(a + age + b); → "나는 30살 입니다."
```
---