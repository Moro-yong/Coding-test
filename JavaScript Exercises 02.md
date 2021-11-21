
<blockquote>

### 문제
reverse 함수에 정수인 숫자를 인자로 받습니다. 그 숫자를 뒤집어서 return해주세요.

x: 숫자 return: 뒤집어진 숫자를 반환!

예들 들어, x: 1234 return: 4321

x: -1234 return: -4321

x: 1230 return: 321</blockquote>


#### 문제 이해하기

* 순회하면서 두 수를 더한다.
* 해당 값이 ```target```이면 리턴한다.

#### 첫 풀이
```js
const reverse = x => {

  let arr = String(x)
  if (arr[0] === '-') {
    arr = arr.slice(1, arr.length)
  } 
  
  let tmp = '';
  for (let i = 0; i<arr.length; i++) {
    tmp += arr[arr.length-i] 
  }
  
  if (x < 0) tmp = '-'+tmp
  return Number(tmp)
}

let x = -1234;
console.log(reverse(x))
```


#### 수정된 풀이
```js
const reverse = x => {
  let arr = String(x) // number x 를 string으로 변경
  if (arr[0] === '-') { // string x의 index 0에 '-'가 있는지 확인(음수인지 판별)
    arr = arr.slice(1, arr.length) // '-'를 제거하여 양수로 변경
    
  } 
  let tmp = ''; //빈 문자열을 생성
  for (let i = 0; i<arr.length; i++) {
    tmp += arr[arr.length-1-i] 
   //arr.length = 4이고, arr의 맨 뒤의 인덱스는 3이다. i=0부터 순회하기 때문에 arr[arr.length-1-i] = arr[4-1-0]이 되어야 arr[3] = 4를 빈 문자열과 더해서 '4'(string)가 만들어진다. 그리고 i = 1이 되고 arr의 크기인 4보다 작을 때 까지 반복하여 tmp = 문자'4321'을 만든다.
  }
  if (x < 0) tmp = '-'+tmp // for문에서 만든 '4321'은 음수였다면 tmp에 '-'를 더해서 '-4321'로 만든다.
  return Number(tmp) // '-4321'은 문자이기 때문에 Number()를 사용해서 숫자로 변경하여 리턴한다.
}

let x = -1234;
console.log(reverse(x)) // -4321
```


#### 다른 풀이 생각해보기
```js
const reverse = x => {
  let temp = `${x}` // 백틱을 사용하여 문자열로 변경
  temp = temp.split('').reverse().join('');
  temp = temp[temp.length-1] === '-' ? '-'+temp.slice(0,temp.length-1) : temp
  return Number(temp)
}
console.log(reverse(-1234))
```










