# Python에서 입력값을 받는 방법

### ❇️ input()보다 빠르게 입력받기

[입력]

```
one
two
three
```



1. `sys.stdin.readline()`

   >  문자열 형태로 개행문자(`\n`)를 포함한 한 줄만 입력된다.

   [출력]

   ```
   one
   ```

   

2. `sys.stdin.realines()`

   > 파일의 끝까지 한 번에 읽어와 각 줄에 개행문자(`\n`)가 포함되어 리스트로 저장된다.

   [출력]

   ```
   ['one\n', 'two\n', 'three\n']
   ```

   

3. `sys.stdin.read()`

   > 파일의 끝까지 한 번에 읽어오고 읽은대로 출력된다.

   [출력]

   ```
   one
   two
   three
   ```

   

4. `sys.stdin.read().splitlines()`

   > 파일의 끝까지 한 번에 읽어오고 개행문자(`\n`)를 제외하여 리스트로 읽는다.

   [출력]

   ```
   ['one', 'two', 'three']
   ```

   