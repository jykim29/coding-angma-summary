# 4강. 형변환
## 선요약
- `String()` : 문자형으로 변환
- `Number()` : 숫자형으로 변환
- `Boolean()` : 불린형으로 변환
---
## prompt로 입력 받았을 때
- 예시
```javascript
// 수학과 영어 점수를 입력받아 평균을 구하는 코드
const mathScore = prompt("수학은 몇점?"); // 90 입력
const engScore = prompt("영어는 몇점?"); // 80 입력
const result = (mathScore + engScore) / 2;
console.log(result);
// 결과는 이상하게 4540이 뜨게 된다.
```
- 4540이 뜨게 된 이유
   1. prompt로 입력받는 경우 문자형이 된다.
   2. 문자와 문자를 더하면 서로 이어붙는다.
   3. 그러므로 `(mathScore + engScore)`은 `"9080"`이라는 문자형이 된다.
   4. 그런데 왜 `"9080" / 2` 은 정상적으로 계산이 되었을까?
→ 나누기 같은 표현식은 숫자형으로 자동적으로 변환이 된다. 이러한 과정을 **자동 형 변환** 이라고 한다.

- 자동으로 형변환이 되서 편리하다고 생각되지만 생각치 않은 오류가 발생할 수 있다.  
  → 항상 의도를 가지고 **명시적 형변환** 을 해야한다.
---
## 명시적 형변환
- `String() `: 괄호 안에 타입을 문자형으로 바꿔준다. (대문자 주의)
```javascript
console.log(
String(3),
String(ture),
String(false),
String(null),
String(undefined)
);
// 결과:  "3" "true" "false" "null" "undefined"
// console.log는 쉼표로 구분하여 여러가지 요소를 한번에 출력할 수 있다.
```
- `Number()` : 괄호 안에 타입을 숫자형으로 바꿔준다. (대문자 주의), 문자형일 경우 자주 사용된다.
```javascript
console.log(
Number("1234"), // 결과: 1234
Number("1234abcd"), // 결과: NaN (문자가 섞여있으면 안된다.)
Number("true"), // 결과: 1
Number("false"), // 결과: 0
);
```
- `Boolean()` : 괄호 안에 타입을 불린형으로 바꿔준다. (대문자 주의)
 - `false`가 되는 경우
    1. 숫자 0
    2. 빈 문자열 `""`
    3. `null`
    4. `undefined`
    5. `NaN`
 - `true`가 되는 경우
    1. 위 5가지 경우 이외
---
## 주의사항
- Number(null)은 0이 된다.
- Number(undefined)는 NaN이 된다.
- Boolean(0)은 false가 된다. *// 숫자 0*
- Boolean("0")은 true가 된다. *// 문자열 0*
- Boolean("")은 false가 된다. *// 빈 문자열*
- Boolean(" ")은 true가 된다. *// 공백 문자열*
- **<span style="color:red">그냥 외우자.</span>**