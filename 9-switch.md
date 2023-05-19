# 9강. 스위치문(switch)
## 스위치문의 장점
- case를 보다 간결하게 쓸 수 있다.
---
## 기본형
```javascript
switch(평가) {
  case A:
  // A일 때 코드
  case B:
  // B일 때 코드
  // ...
  default :
  // 평가에 없을 때 코드
}
```
- 만약 `case`마다 `break`가 없다면 모든 `case`문이 실행된다.  
  그러므로 `case`마다 `break`문을 넣어서 `case` 안의 코드가 끝나면 `switch`문을 빠져나오도록 한다.
  