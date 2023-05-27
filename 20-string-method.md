# 중급 6강. 문자열 메소드(String method)
## 작은따옴표(single quote), 큰따옴표(double quote), 백틱(backtick)
- 작은따옴표('') : html코드를 적을 때 편하다. (문자열 내 큰따옴표 때문)
- 큰따옴표("") : 문장을 적을 때 편하다. (문자열 내 작은따옴표 때문)
- 백틱 : 문자열 내 변수와 같이 적을 때 편하다.(변수는 ${변수} 사용)
  - 백틱은 따옴표와 다르게 한 문자열을 여러줄로 쓸 수 있다.
---
## 길이를 반환하는 length 메소드
- `string.length`
- 문자열 변수 뒤에 .length를 붙여 그 문자열의 길이를 반환한다.
  ```js
  let desc = '안녕하세요.';
  desc.length;  // 길이 6 반환
  ```
---
## 배열과 동일하게 특정 위치에 접근 가능
- `str[i]`
- 배열처럼 변수 뒤에 [인덱스]를 붙여 특정 인덱스에 접근이 가능하다.  
  대신 배열과 다르게 특정 인덱스의 글자만 변경하는 것은 불가능하다.
  ```js
  let desc = '안녕하세요.';
  desc[1];  // '녕' 반환
  desc[4] = '용'  // 동작하지 않는다.
  console.log(desc) // 용으로 바뀌지 않고 그대로 '안녕하세요' 출력
  ```
---
## 대/소문자로 바꿔주는 toUpperCase()와 toLowerCase() 메소드
- `str.toUpperCase(), str.toLowerCase()`
- 문자열을 대문자로 바꿔주는 toUpperCase()
  ```js
  let desc = 'hello world.';
  desc.toUpperCase(); // 'HELLO WORLD'로 변환
  ```
- 문자열을 소문자로 바꿔주는 toUpperCase()
  ```js
  let desc = 'HELLO WORLD.';
  desc.toLowerCase(); // 'hello world'로 변환
  ```
---
## 문자의 인덱스 위치를 탐색하는 indexOf() 메소드
- `indexOf(문자)`
- indexOf()는 문자를 인수로 받아 해당 문자의 인덱스 위치를 반환한다.
  포함되어 있는 문자가 여러개라도 첫 번째 인덱스위치만 반환한다.
  만약 포함되어 있지 않다면 -1을 반환한다.
  ```js
  let desc = 'How are you?';
  desc.indexOf('are'); // 4 반환
  desc.indexOf('is'); // 없으므로 -1 반환
  ```
---
## 특정 범위의 문자열를 반환하는 slice() 메소드
- `slice(n, m)` // `n` : 시작 인덱스, `m` : 끝 인덱스
- 문자열의 특정 범위만 추출하고 싶을 때 사용한다. 인수는 시작인덱스, 끝인덱스 순서로 2개를 받는다.  
추출범위는 시작인덱스 ~ 끝인덱스 직전까지이며 끝인덱스의 문자는 포함하지 않는다.  
만약 끝인덱스를 생략할 경우 그 문자열의 끝까지 추출한다.  
음수일 경우 끝에서부터 -1을 시작으로 거꾸로 센다.
  ```js
  let desc = 'abcdefg';
  desc.slice(2);  // 'cdefg' 반환
  desc.slice(0, 5); // 'abcde' 반환
  desc.slice(2, -2);  // 'cde' 반환
  ```
---
## 두 인덱스 사이의 문자열을 반환하는 substring() 메소드
- `substring(n, m)` // `n` : 시작 인덱스, `m` : 끝 인덱스 // 순서 상관없음
- slice()와 마찬가지로 2개의 인수를 받으나, 시작과 끝의 순서를 바꿔도 상관없으며 단순히 시작~끝 사이의 문자를 반환한다.  
음수는 0으로 인식한다.
  ```js
  let desc = 'abcdefg';
  desc.substring(2, 5); // 'cde' 반환
  desc.substring(5, 2); // 순서 상관없이 'cde' 반환
  ```
## 시작 인덱스부터 특정 개수까지 문자열을 반환하는 substr() 메소드
- `substring(n, m)` // `n` : 시작 인덱스, `m` : 시작인덱스부터 m개를 반환
- `substring()`과는 다르게 시작 인덱스부터 특정 개수를 세어 문자열로 반환한다.
  ```js
  let desc = 'abcdefg';
  desc.substr(2, 4);  // 'cdef' 반환
  desc.substr(-4, 2); // 'de' 반환
  ```
---
## 앞 뒤 공백을 제거하는 trim()메소드
- `str.trim()`
- 문자열 앞 뒤 공백을 제거한 문자열을 반환한다.
  ```js
  let desc = '  hello world.    ';
  desc.trim();  // 앞뒤 공백 제거한 'hello world' 반환
  ```
---
## 문자열을 반복하는 repeat() 메소드
- `str.repeat(n)` : `n` // 반복 횟수
  ```js
  let desc = 'hello';
  desc.repeat(3); // 3번 반복하는 'hellohellohello' 반환
  ```
---
## 문자열 비교 원리
- 숫자처럼 문자도 비교가 가능하다.
- 아스키 코드의 10진법에 근거하여 크기를 비교한다.
- 예를 들어 `'a' < 'c'` 이다.
---
## 아스키코드를 구하거나 불러오는 codePointAt()과 fromCodePoint() 메소드
- 특정 문자의 아스키코드를 불러오거나, 특정 아스키코드에 해당하는 문자를 불러올 때 사용한다.
  ```js
  'a'.codePointAt(); // 97
  string.fromCodePoint(97); // 'a'
  ```
---

