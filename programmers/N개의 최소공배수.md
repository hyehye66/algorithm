[Python]

1. LCM(최소공배수) 함수와 GCD(최대공약수) 함수 이용

   ```python
   def gcd(a, b):
       while b > 0:
           a, b = b, a % b
       return a
   
   
   def lcm(a, b):
       return a * b / gcd(a, b)
   
   
   def solution(arr):
       while len(arr) > 1:
           a = arr.pop(0)
           b = arr.pop(0)        
           arr.append(lcm(a, b))
       return arr[0]
   ```

   

2. LCM만

   ```python
   def lcm(a, b):
       for i in range(max(a, b), (a * b) + 1):
           if i % a == 0 and i % b == 0:
               return i
           
   def solution(arr):
       while len(arr) > 1:
           a = arr.pop(0)
           b = arr.pop(0)
           arr.append(lcm(a, b))
       
       return arr[0]
   ```



[JavaScript]

```javascript
function lcm(a, b) {
    for (let i=Math.max(a,b);i<(a*b)+1;i++) {
        if (i%a==0 && i%b==0) {
            return i
        }
    }
}

function solution(arr) {
    while (arr.length > 1) {
        let a = arr.pop();
        let b = arr.pop();
        arr.push(lcm(a, b));
    }
    return arr[0]        
}
```

