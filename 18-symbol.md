# 중급 4강. 심볼(Symbol)
##  심볼(Symbol)
- 심볼은 유일한 식별자로 서로 다른 변수에 똑같이 symbol();을 할당해도 두 변수는 다른 값을 가지게 된다.
```js
const a = Symbol();
const b = Symbol();
console.log(a === b); // false
console.log(a == b);  // false
```
- 심볼은 소괄호 사이에 설명을 붙여줄 수도 있다. 하지만 유일성이 보장되기 때문에 같은 설명의 심볼들은 서로 같지 않다고 나온다.
```js
const id = Symbol('id'); // 심볼에 id라는 설명을 붙여줬다.
const id2 = Symbol('id');
console.log(id === id2); // false
console.log(id == id2);  // false
```
- 심볼은 객체 프로퍼티 키(property key)로도 사용할 수 있다.
```js
const id = Symbol('id');
const user = {
  name : 'Mike',
  age : 23,
  [id] : 'myid' // id라는 심볼을 computed key로 할당했다.
}
```
- 심볼은 오브젝트 메서드에서는 나타나지 않는다.
```js
const id = Symbol('id');
const user = {
  name : 'Mike',
  age : 23,
  [id] : 'myid'
}
Object.keys(user); // ['name', 'age'] 
Object.values(user);  // ['Mike', 23]
Object.entries(user); // [['name', 'Mike'] , ['age', 23]]
for(let i in user) {...}  // 심볼 프로퍼티는 해당없음
```
---
# 전역 심볼
## Symbol.for()
- 하나의 심볼만 보장받을 수 있다.
- '전역'이기 때문에 코드 어디서든 사용할 수 있다.
- 없으면 만들게되고, 있으면 가져오기 때문이다.
- Symbol함수는 매번 다른 값의 Symbol을 생성하지만
- Symbol.for 메서드는 하나를 생성한 뒤 키를 통해 같은 Symbol을 공유한다.
```js
const id1 = Symbol.for('id');
const id2 = Symbol.for('id');
console.log(id1 == id2);  // true 출력
console.log(id1 === id2); // true 출력
```
- `Symbol.keyFor(변수명)` : 전역 심볼을 생성할 때 만들었던 이름을 알려준다.
- `변수명.description` : 전역 심볼이 아닐 경우 만들었던 이름을 알려준다.