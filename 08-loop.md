# 8강. 반복문 (for, while, do while)
## 기본 구조
- for문
```javascript
for(let i = 0 ; i < 10 ; i++) {
  // 반복할 코드
}
```
- while문
```javascript
let i = 0;
while (i < 10>) {
  // 반복할 코드
  i++;
}
```
- do while문
```javascript
let i = 0;
do  {
  // 반복할 코드
  i++;
} while (i < 10)
```
---
## while과 do while의 차이점
- `while`은 먼저 조건을 체크하고 코드를 실행하며 `do while`은 먼저 코드를 1번 실행한 후 조건을 체크한다.
---
## break, continue
- `break` : 멈추고 빠져나온다.
```javascript
// confirm창 확인을 누르면 계속 켜지고 취소를 누르면 꺼지는 코드
while(true) {
  let answer = confirm('계속 할까요?');
  if(!answer) {  // 취소를 누르면 !0이된다. 즉, 1이 되기때문에 break 
    break;
  }
}
```
- `continue` : 멈추고 다음 반복으로 진행한다.
```javascript
// 짝수만 골라내는 코드
for(let i = 0 ; i < 10 ; i++) {
  if(i % 2) {  
    continue;  // 2로 나눈 나머지가 1일 경우 continue로 다시 반복문
  }
  console.log(i);
}
// 결과 : 0 2 4 6 8 ....
```

