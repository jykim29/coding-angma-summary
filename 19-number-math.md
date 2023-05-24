# 중급 5강. 숫자, 수학 메서드 (Number, Math method)
## toString()
- 숫자를 문자열로 변환한다.
- 문자열로 변환할 때 다양한 진수법으로 변환 할 수 있다.
```js
let num = 10;
num.toString(); // '10' 10진수
num.toString(2); // '1001' 2진수
num.toString(8);  // '12' 8진수
num.toString(16); // 'a' 16진수
```
---
## Math.ceil()
- 숫자를 올림한다.
```js
let num1 = 5.7;
let num2 = 2.2;
Math.ceil(num1);  // 6
Math.ceil(num2);  // 3
```
---
## Math.floor()
- 숫자를 내림한다.
```js
let num1 = 5.7;
let num2 = 2.2;
Math.floor(num1);  // 5
Math.floor(num2);  // 2
```
---
## Math.round()
- 숫자를 반올림한다.
```js
let num1 = 5.7;
let num2 = 2.2;
Math.round(num1);  // 6
Math.round(num2);  // 2
```
---
## .toFixed()
- 소수점 자릿수를 정하고 **'문자열'** 로 반환한다.
```js
let userRate = 30.1457;
userRate.toFixed(0);  // '30'
userRate.toFixed(2);  // '30.15'
userRate.toFixed(6);  // '30.145700'
Number(userRate.toFixed(2));  // 30.15, Number()를 이용해 숫자로 변환해준다.
```
## isNaN()
- **NaN(Not a Number)** 인지 판별해준다. <u>오직 isNaN만이 NaN인지 아닌지 판별해준다.</u>
```js
let x = Number('a');  // NaN
x == NaN  // false
NaN == NaN  // false, isNaN이 아닌 비교는 무조건 false를 내뱉는다.
isNaN(x);  // true, isNaN을 써야지 비로소 정상적으로 작동한다.
```
---
## parseInt()
- `parseInt()`는 `Number()`와 다르게 숫자 외에 문자가 섞여있어도, 숫자를 읽을 수 있는 만큼 읽고 10진수형태의 숫자로 반환한다.
```js
let margin = '10px';
Number(margin); // NaN
parseInt(margin); // 10
let redColor = 'f3';
parseInt(redColor); // NaN, 첫글자부터 문자인경우, 읽지못하고 NaN을 반환한다.
```
- `parseInt()`는 두번째 인수를 지정받아 대상 문자열의 진수를 지정할 수 있다.
```js
let redColor = 'f3';
parseInt(redColor, 16); // 243, 'f3'를 16진수로 지정받아 10진수인 243으로 반환한다.
parseInt('11', 2); // 3, '11'을 2진수로 지정받아 10진수인 3으로 반환한다.
```
---
## parseFloat()
- `parseInt()`는 정수로 반환하는 것과 다르게 `parseFloat()`은 부동소수점 형태로 반환한다.
```js
let padding = '25.5%';
parseFloat(padding);  // 25.5
```
## Math.random()
- 0 ~ 1 사이의 랜덤한 숫자를 반환한다.
- 만약 0 ~ n 사이의 랜덤한 숫자를 뽑고 싶으면
  `(Math.random() * n) + 1`의 값에서 `Math.floor()`를 해주면 소수점이 사라지고 정수만 뽑을 수 있게된다.  
```js
// 0 ~ 100 사이의 랜덤 숫자 반환
Math.floor( (Math.random() * n) + 1 );
```
---
## Math.max()와 Math.min()
- 소괄호 안의 인수들 중 최대값 또는 최소값을 반환한다.
```js
Math.max(1, 4, -1, 5, 10, 9, 5.54); // 10
Math.min(1, 4, -1, 5, 10, 9, 5.54); // -1
```
---
## Math.abs()
- 소괄호 안의 인수의 절대값을 반환한다.  
```js
Math.abs(-5);  // 5
```
---
## Math.pow(n, m)
- 인수 n을 m제곱한 값을 반환한다.
```js
Math.pow(2, 10);  // 2의 10제곱 : 1024
```
---
## Math.sqrt()
- 인수의 제곱근을 반환한다
```js
Math.sqrt(16);  // 16의 제곱근 : 4
```
