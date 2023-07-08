# match-case 문

✨ *Python 3.10에 새로 추가된 구문* ✨

`switch-case` 문과 비슷하면서 다른 기능도 지니고 있다.

1. 기본 사용 형태

   ```python
   for n in range(1, 7):
       match n % 3:
           case 0:
               print(f"{n} is a multiple of 3.")
           case 1:
               print(f"{n} is not a multiple of 3.")
           case 2:
               print(f"{n} is not a multiple of 3.")
   ```

   `n`을 3으로 나눈 나머지가 0이면 3의 배수(a multiple of 3), 1이나 2이면 3의 배수가 아니라고 출력한다.

   

2. 인자가 tuple 형식일 때

   ```python
   for n in range(1, 7):
       match (n % 2, n % 3):
           case (0, 0):
               print("TwoThree")
           case (0, _):
               print("Two")
           case (_, 0):
               print("Three")
           case _:
               print(n)
   ```
   
    [output]

   ```markdown
   1
   Two
   Three
   Two
   5
   TwoThree
   ```
   
   - `case (0, 0):` :  “`n`을 2으로 나눈 나머지도 0이고, 3로 나눈 나머지도 0인 경우”를 의미한다. 만족할 경우 ‘TwoThree’를 출력한다.
   - `case (0, _):` :  “`n`을 2로 나눈 나머지가 0인 경우”를 의미한다. `case` 문에서 밑줄(`_`)은 아무 값이나 상관없다는 뜻.
   - `case (_, 0):` : "`n`을 3으로 나누어 떨어지는 경우"
   - `case _:` : 그 밖의 모든 경우. 2나 3으로 나누어 떨어지지 않는 숫자들이다.
   
   

3. 고정되지 않은 개수의 인자들일 때

   ```python
   def greeting(message):
       match message:
           case ["hello"]:
               print("Hello!")
           case ["hello", name]:
               print(f"Hello {name}!")
           case ["hello", *names]:
               for name in names:
                   print(f"Hello {name}!")
           case _:
               print("see you")
   ```

   ```python
   greeting(["hello"])
   greeting(["hello", "Geunhye"])
   greeting(["hello", "Geunhye", "Woo", "Bae"])
   ```

   

4. 가드

   패턴에 if문을 넣는 것을 `가드`라고 한다. 가드가 False이면 다음 case 문을 실행한다.

   ```python
   match compare:
       case (x, y) if x == y:
           print(f"{x} and {y} are same.")
       case (x, y):
           print(f"{x} and {y} are different.")
   ```

   

---

