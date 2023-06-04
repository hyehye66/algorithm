# itertools

Python에서 제공하는 자신만의 반복자를 만드는 모듈



## 🔎 itertools.islice

🔶`itertools.islice`(*iterable*, *stop*)

- iterable에서 stop 지점에서 멈추고 그 지점 전까지 잘라준다.

🔶`itertools.islice`(*iterable*, *start*, *stop*[, *step*])

- *start*가 `None`이면, 이터레이션은 0에서 시작한다. *step*이 `None`이면, step의 기본값은 1이다.
- step은 각 반복 후 건너뛸 수 있는 단계
- *start*, *stop* 또는 *step*에 대해 음수 값을 지원하지 않는다.

```python
from itertools import islice

for i in islice(range(10), 5):
    print i
# 출력 : 0 1 2 3 4

for i in islice(range(100), 0, 100, 10):
    print i
# 출력 : 0 10 20 30 40 50 60 70 80 90
```



참고자료)

https://docs.python.org/ko/3.8/library/itertools.html