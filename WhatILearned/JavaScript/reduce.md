# 🔎reduce()

`reduce()` 메서드는 배열의 각 요소에 대해 주어진 리듀서 (reducer) 함수를 실행하고, 하나의 결과값을 반환한다.



## 리듀서 함수의 4가지 인자

1. 누산기 (acc)
2. 현재 값 (cur)
3. 현재 인덱스 (idx)
4. 원본 배열 (src)

리듀서 함수의 반환 값은 누산기에 할당되고, 누산기는 순회 중 유지되므로 결국 하나의 값(누적 계산의 결과 값)이 최종적으로 반환된다.



## 형태

```javascript
arr.reduce(callback[, initialValue])
```



## 매개변수

- [`callback`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce#callback)

  - [`accumulator`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce#accumulator): 누산기는 콜백의 반환값을 누적한다. 콜백의 이전 반환값 또는, 콜백의 첫 번째 호출이면서 `initialValue`를 제공한 경우에는 `initialValue`의 값이다.
  - [`currentValue`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce#currentvalue): 처리할 현재 요소.
  - [`currentIndex`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce#currentindex) : Optional처리할 현재 요소의 인덱스. `initialValue`를 제공한 경우 0, 아니면 1부터 시작합니다.
  - [`array`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce#array): Optional`reduce()`를 호출한 배열.

- [`initialValue`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce#initialvalue) Optional

  `callback`의 최초 호출에서 첫 번째 인수에 제공하는 값. 초기값을 제공하지 않으면 배열의 첫 번째 요소를 사용한다. 빈 배열에서 초기값 없이 `reduce()`를 호출하면 오류가 발생한다.

- 만약 `reduce()` 함수 호출에서 `initialValue`를 제공한 경우, `accumulator`는 `initialValue`와 같고 `currentValue`는 배열의 첫 번째 값과 같다. 
- `initialValue`를 제공하지 않았다면, `accumulator`는 배열의 첫 번째 값과 같고 `currentValue`는 두 번째와 같다. 
- 🚨 **`initialValue`를 제공하지 않으면, `reduce()`는 인덱스 1부터 시작해 콜백 함수를 실행하고 첫 번째 인덱스는 건너 뛴다. `initialValue`를 제공하면 인덱스 0에서 시작한다.**🚨



## 예시

1. initialValue가 없을 때

   ```javascript
   [0, 1, 2, 3, 4].reduce(
     function (accumulator, currentValue, currentIndex, array) {
       return accumulator + currentValue;
     },
   ); // 반환값:10 
   ```

   

2. initialValue가 있을 때

   ```javascript
   A = [0,1]
   B = [6,7]
   A.reduce((total, val, idx) => total + val * B[idx], 0) // 반환값:14
   ```

   

