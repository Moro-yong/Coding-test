<blockquote>

### 문제
String 형인 str 인자에서 중복되지 않은 알파벳으로 이루어진 제일 긴 단어의 길이를 반환해주세요.

str: 텍스트 return: 중복되지 않은 알파벳 길이 (숫자 반환)

예를 들어, str = "abcabcabc" return 은 3 => 'abc' 가 제일 길기 때문

str = "aaaaa" return 은 1 => 'a' 가 제일 길기 때문

str = "sttrg" return 은 3 => 'trg' 가 제일 길기 때문
</blockquote>


#### 첫 풀이
```js
const getLengthOfStr = str => {
  let s = 0;
  let e = 0;
  let tmp = '';
  let answer = 0;
  
  while (e < str.length) {
    if (tmp.indexOf(str[e]) === -1){
      tmp += str[e];
      e++;
    } else {
      if (answer < tmp.length)
        answer = tmp.length
      tmp = ''
      s += e
    }
  }

  if (answer < tmp.length)
    answer = tmp.length

  return answer
}

console.log(getLengthOfStr('sttrgvjydchgcdhs'))
```

#### 수정된 풀이
```js
const getLengthOfStr = str => {
  // 아래 코드를 작성해주세요.
  let answer = 0;
  for (let i=0; i<str.length; i++){
    let s = i;
    let e = i;
    let tmp = '';
    while (e < str.length) {
      if (tmp.indexOf(str[e]) === -1){
        tmp += str[e];
        console.log(tmp)
        e++;
      } else {
        if (answer < tmp.length)
        answer = tmp.length
        tmp = ''
        s += e
      }
    }
    if (answer < tmp.length) answer = tmp.length
  }
  return answer
}
console.log(getLengthOfStr('https'))
```
