## 문제 설명

함수 solution은 정수 x와 자연수 n을 입력 받아, x부터 시작해 x씩 증가하는 숫자를 n개 지니는 리스트를 리턴해야 합니다. 다음 제한 조건을 보고, 조건을 만족하는 함수, solution을 완성해주세요.

## 제한 조건
- x는 -10000000 이상, 10000000 이하인 정수입니다.
- n은 1000 이하인 자연수입니다.

## 입출력 예

| x   | n   | answer       |
| --- | --- | ------------ |
| 2   | 5   | [2,4,6,8,10] |
| 4   | 3   | [4,8,12]     |
| -4  | 2   | [-4, -8]     |

## 접근

n번 반복하는 반복문을 만든다. 그 안에서 x부터 answer 배열에 집어넣되, 반복할 때마다 x씩 증가시켜 집어넣는다.

## 구현

```js
const solution = (x, n) => {
    let answer = [];
    let value = x; // 배열에 들어갈 값 초기화
    
    // n번 반복
    for (let i = 0; i < n; i++) {
        answer.push(value); // 초기값 넣기
        value += x; // x만큼 증가
    }
    
    return answer;
};
```

## 다른 사람의 풀이

`Array.prototype.fill()`과 `Array.prototype.map()`을 이용한 멋진 풀이.

나도 이렇게 함수형으로 잘 풀어보고 싶다.

```js
function solution(x, n) {
    return Array(n).fill(x).map((v, i) => (i + 1) * v)
}
```

### Array.prototype.fill()

> https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/fill

빈 배열을 만들 때 반복문을 사용하곤 했는데

아래 구문처럼 작성하면 반복문 없이도 빈 배열을 만들 수 있겠다.

```js
Array(3).fill(0);
```

### 예제

```js
[1, 2, 3].fill(4);               // [4, 4, 4]
[1, 2, 3].fill(4, 1);            // [1, 4, 4]
[1, 2, 3].fill(4, 1, 2);         // [1, 4, 3]
[1, 2, 3].fill(4, 1, 1);         // [1, 2, 3]
[1, 2, 3].fill(4, 3, 3);         // [1, 2, 3]
[1, 2, 3].fill(4, -3, -2);       // [4, 2, 3]
[1, 2, 3].fill(4, NaN, NaN);     // [1, 2, 3]
[1, 2, 3].fill(4, 3, 5);         // [1, 2, 3]
Array(3).fill(4);                // [4, 4, 4]
[].fill.call({ length: 3 }, 4);  // {0: 4, 1: 4, 2: 4, length: 3}

// Objects by reference.
var arr = Array(3).fill({}); // [{}, {}, {}]
arr[0].hi = "hi"; // [{ hi: "hi" }, { hi: "hi" }, { hi: "hi" }]
```