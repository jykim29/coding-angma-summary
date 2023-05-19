# 3강. alert, prompt, confirm
## alert()
- 메세지를 띄우고 사용자가 확인버튼을 누르기 전까지는 계속 떠있는다. 주로 경고의 의미로 사용된다.
```javascript
alert("아이디를 입력해주세요."); 
```
---
## prompt()
- 사용자에 의해 어떤 값을 입력 받을 때 사용된다.
```javascript
// double quote로 표현
const name = prompt("이름 입력");
alert("환영합니다. "+name+"님");

// backtick으로 표현
const name = prompt("이름 입력");
alert(`환영합니다. ${name}님`);
```
- 취소버튼을 누르면 `null`값이 입력된다.
- 두개의 인수를 받아 default 값도 입력할 수 있다.
```javascript
// 두번째 인수가 default 값이 되어 텍스트창에 미리 입력된다.
const name = prompt("날짜를 입력해주세요.", "2023-05-");
```
---
## confirm()
- `alert();`과 다른점은 alert은 확인버튼만 있는 반면, `confirm();`은 취소버튼도 있다.
- 확인을 누를 경우 `true`가되고 취소를 누를 경우 `false`가 된다.
```javascript
// 확인을 누르면 isAdult는 true, 취소를 누르면 isAdult는 false
const isAdult = confirm("성인이십니까?");
console.log(isAdult);
```
---
## 단점
1. 창이 떠있는동안 스크립트가 정지된다.
2. 스타일링이 불가능하다. → CSS의 Modal 창으로 대체하고 있다.