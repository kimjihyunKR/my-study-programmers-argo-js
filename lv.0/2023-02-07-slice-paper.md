# Slice paper

```js
function solution(M, N) {
    var answer = 0;
    // N-1 + (M-1)*N;
    answer = N * M - 1;
    return answer;
}
```