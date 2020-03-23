# algorithm-dataStructure-JS
주니어 개발자 코딩 테스트를 대비하여 자바스크립트로 알고리즘과 자료구조를 구현합니다.

> 패스트캠퍼스 코딩테스트 인터넷 강의를 참고했습니다.

## 알고리즘

### 버블정렬

두 인접한 데이터를 비교해서 앞에 있는 데이터가 뒤에 있는 데이터보다 크면 자리를 바꾸는 정렬.

<img src="https://upload.wikimedia.org/wikipedia/commons/c/c8/Bubble-sort-example-300px.gif" width=600/>

> 예시: https://visualgo.net/en/sorting

#### 구현

```js
const bubblesort = data => {
  // 크기 비교를 전체 데이터 길이 -1만큼 반복
  for (let i = 0; i < data.length - 1; i++) {
    let swap = false; // 변화가 있는지 없는지 확인
    for (let j = 0; j < data.length - i - 1; j++) {
      // 앞 데이터가 뒤 데이터보다 크다면
      if (data[j] > data[j + 1]) {
        // 스와핑
        [data[j], data[j + 1]] = [data[j + 1], data[j]];
        swap = true;
      }
    }
    // 비교했는데 변화가 없다는 것은 이미 정렬이 완료된 것이므로 종료
    if (!swap) {
      break;
    }
  }
  return data;
}

const array = [12, 44, 56, 34, 87, 32, 75, 1, 3, 6, 2];

console.log(bubblesort(array));
```

#### 시간복잡도
반복문 두 개. n의 2제곱.
