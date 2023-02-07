# Next Number 다음에 올 숫자

등차수열(arithmetic sequence) : 연속된 숫자가 특정한 차이로 이뤄진 수열   
등비수열(geometric sequence) : 연속된 숫자가 특정한 비율로 이뤄진 수열

- 등차수열인지 등비 수열인지 찾기
  - `n-1`, `n`, `n+1`번째 value의 차이가 일정한가? => 등차수열
  - `n-1`, `n`, `n+1`번째 value의 나누기 결과가 같은가? => 등비수열

```js
// 등차수열(arithmetic sequence) 이하 AS
// 등비수열(geometric sequence) 이하 GS

function solution(common) {
    var answer = 0;

    if(isAS(common)) {
        answer = getNextNumInAS(common);
    } else if(isGS(common)) {
        answer = getNextNumInGS(common);
    }
    return answer;
}

function  isAS(arr) {
    const diff1 = arr[1] - arr[0];
    const diff2 = arr[2] - arr[1];
    return diff1 === diff2
}

function isGS(arr) {
    const ratio1 = arr[1] / arr[0];
    const ratio2 = arr[2] / arr[1];
    return ratio1 === ratio2
}

function getNextNumInAS(arr) {
    const diff = arr[1] - arr[0]; // 등차
    const lastValue = arr[arr.length-1];
    return lastValue + diff
}

function getNextNumInGS(arr) {
    const ratio = arr[1] / arr[0]; // 등비
     const lastValue = arr[arr.length-1];
    return lastValue * ratio
}
```