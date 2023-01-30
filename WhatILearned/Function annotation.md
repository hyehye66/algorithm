# Function annotation

python은 변수나 함수 사용시 자료형에 대한 선언이 없고 자유롭게 사용이 가능하기 때문에 작성된 코드를 볼때 명시적으로 해석이 어려운 부분이 있다. 이를 개선하기 위해 나온 기능이 `Function annotation` 이다.

python3 이상에서 사용가능하다.



### 사용방법

> #### example
>
> ```python
> # Fuctnion annotation
> def func(arg1: int, arg2: 4-3, arg3: 'Do you know Function annotation?') -> bool
> ```
>
> - annotation에는 매개변수의 type(ex. arg1)이나 사칙연산 같은 간단한 연산 표현(ex. arg2) 혹은 string 형태(ex. arg3)로 파라미터에 `: expression` 형태로 쓸 수 있다.
>
> - function의 return 값에 대해서 `-> expression` 형태로 사용한다. return 또한 매개변수와 사용 방법이 같다.
>
> 



### 특징

- 강제성이 없다. 

주석일 뿐이고 해당 code 자체에 영향을 끼치지 않는다.



### 장점

- 함수의 매개변수와 반환값을 명시적으로 보여준다.

​	annotation 을 활용해 명시적으로 해당 변수를 지정하는 경우, IDE 에서 인식 가능하다.