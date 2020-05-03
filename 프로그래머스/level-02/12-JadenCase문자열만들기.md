## 문제 설명

JadenCase란 모든 단어의 첫 문자가 대문자이고, 그 외의 알파벳은 소문자인 문자열입니다. 문자열 s가 주어졌을 때, s를 JadenCase로 바꾼 문자열을 리턴하는 함수, solution을 완성해주세요.

## 제한 조건

- s는 길이 1 이상인 문자열입니다.
- s는 알파벳과 공백문자(" ")로 이루어져 있습니다.
- 첫 문자가 영문이 아닐때에는 이어지는 영문은 소문자로 씁니다. ( 첫번째 입출력 예 참고 )

## 입출력 예

| s                       | return                  |
| ----------------------- | ----------------------- |
| "3people unFollowed me" | "3people Unfollowed Me" |
| "for the last week"     | "For The Last Week"     |

## 접근

일단 주어진 문자열을 모두 소문자로 바꾸고 공백을 기준으로 나누어 배열로 만든다.

해당 배열의 요소를 다시 배열로 나누고, 0번 인덱스(각 단어의 첫 글자)를 대문자로 바꿔준다.

이때 "For The Last  Week"와 같이 연속된 공백을 포함한 문장을 조심해서 처리한다.

## 구현

```js
const solution = s => {
    let answer = '';
    const arr = s.toLowerCase().split(" ");
    const temp = [];

    for (let i = 0; i < arr.length; i++) {
        const letters = arr[i].split("");

        if (letters[0] !== undefined) {
          letters[0] = letters[0].toUpperCase();
        }

        temp.push(letters.join(""));
    }
    
    answer = temp.join(" ");
    return answer;
};
```