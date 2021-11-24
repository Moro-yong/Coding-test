<blockquote>

### 문제
숫자인 num을 인자로 넘겨주면, 뒤집은 모양이 num과 똑같은지 여부를 반환해주세요.

num: 숫자 return: true or false (뒤집은 모양이 num와 똑같은지 여부)

예를 들어, num = 123 return false => 뒤집은 모양이 321 이기 때문

num = 1221 return true => 뒤집은 모양이 1221 이기 때문

num = -121 return false => 뒤집은 모양이 121- 이기 때문

num = 10 return false => 뒤집은 모양이 01 이기 때문
</blockquote>


#### 첫 풀이
```js
const sameReverse = num => {
  if( num < 0 ) return false
    let x = String(num).split('').reverse().join('');
    if( Number(x) === num ) return true;
    return false;
}
console.log(sameReverse(1221))
```


#### 풀이 수정

```js
const sameReverse = num => {
  if (num <0) return false
  let ans = (num === Number(`${num}`.split('').reverse().join('')) ? true :false)
  return ans
}
console.log(sameReverse(1221))
```


#### 다른 풀이
```js
const sameReverse = num => {
  if (num < 0) return false
  
  let stringNum = `${num}`
  let arr = ''
  // console.log(arr)
  // console.log(stringNum)  
  
  for (let i = 0; i < stringNum.length; i++) {
    arr += stringNum[stringNum.length-1-i]
  } 
  if (Number(arr) === num) return true
}
console.log(sameReverse(1221))
```
