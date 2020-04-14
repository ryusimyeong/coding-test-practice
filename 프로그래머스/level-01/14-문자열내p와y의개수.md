## 문제
대문자와 소문자가 섞여있는 문자열 s가 주어집니다. s에 'p'의 개수와 'y'의 개수를 비교해 같으면 True, 다르면 False를 return 하는 solution를 완성하세요. 'p', 'y' 모두 하나도 없는 경우는 항상 True를 리턴합니다. 단, 개수를 비교할 때 대문자와 소문자는 구별하지 않습니다.

예를 들어 s가 "pPoooyY"면 true를 return하고 "Pyy"라면 false를 return합니다.

## 제한 사항
- 문자열 s의 길이 : 50 이하의 자연수
- 문자열 s는 알파벳으로만 이루어져 있습니다.

## 입출력 예
| s       | answer |
| ------- | ------ |
| pPoooyY | true   |
| Pyy     | false  |

### 입출력 예 설명
- 입출력 예 #1
'p'의 개수 2개, 'y'의 개수 2개로 같으므로 true를 return 합니다.

- 입출력 예 #2
'p'의 개수 1개, 'y'의 개수 2개로 다르므로 false를 return 합니다.

## 접근
p, y가 있는 경우와 없는 경우로 나눈다.

주어진 문자열을 한 글자씩 순회하면서 p나 P, y나 Y가 있는지 확인한다.

## 구현
```js
const solution = s => {
    // p, y가 있는 경우
    if (s.includes("p") ||
        s.includes("P") ||
        s.includes("y") ||
        s.includes("Y")) {
        
        let pCount = 0;
        let yCount = 0;
        
        for (let letter of s) {
            if (letter === "p" || letter === "P") 
                pCount++;
            if (letter === "y" || letter === "Y") 
                yCount++;
        }
        
        if (pCount === yCount) return true;
        else return false;
    }
    // p, y 하나도 없는 경우
    return true;
};
```

## 다른 사람의 풀이

와.. 발상 자체가 너무 참신하다.

일단 모두 대문자(혹은 소문자)로 바꾸고

P나 Y로 split을 하면 P나 Y의 개수 만큼 빈 문자열이 생기고, 길이가 P나 Y의 개수 +1인 배열이 생성된다.

```js
function numPY(s){
  //함수를 완성하세요
    return s.toUpperCase().split("P").length === s.toUpperCase().split("Y").length;
}
```