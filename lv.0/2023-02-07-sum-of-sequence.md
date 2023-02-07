# Sum of Sequence 연속된 수의 합

등차수열의 합을 생각해보자.
- a: 첫번째 숫자.
-  예) [1, 2, 3, 4, 5] / 총합 15
```js
// a + a+1 + a+2 + a+3 + a+4 = 15
// 5a + (1+2+3+4) = 15
let a = ( 15 - (1+2+3+4) ) / 5;
```

```js
function solution(num, total) {
    var answer = [];
    let firstNum = (total - sumFromOneToNum(num-1)) / num;
    for(let i=0; i < num; i++) {
        answer.push(firstNum + i);
    }
    return answer;
}


// 1부터 n번 더하기 n*(n+1)/2
function sumFromOneToNum(lastNumber) {
    return lastNumber * (lastNumber+1)/2
}
```