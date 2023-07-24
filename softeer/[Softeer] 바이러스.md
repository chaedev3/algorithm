# [Softeer] 바이러스 

- Python  



##### 문제 

바이러스가 숙주의 몸속에서 1초당 P배씩 증가한다.



처음에 바이러스 K마리가 있었다면 N초 후에는 총 몇 마리의 바이러스로 불어날까? N초 동안 죽는 바이러스는 없다고 가정한다. 

최종 바이러스 개수를 1000000007로 나눈 나머지를 출력하라. 

1 ≤ K ≤ 10 ** 8인 정수, 1 ≤ P ≤ 10 ** 8인 정수, 1 ≤ N ≤ 10 ** 6인 정수



##### 모듈러 산술을 이용한 풀이 

```
(A * B) mod C = (A mod C * B mod C) mod C  
```



이 공식을 이용하면 

N 번 동안 

result = K 부터 시작하여 

result = K * P 

result = K * P * P ... 

이 형식으로 진행되기 때문에 모듈러 산술을 이용해서 풀면 시간 초과 없이 해결할 수 있다.  

result = K 

for _ in range(N):

​	k = result % 1000000007 

​	p = P % 1000000007  

​	result = k * p % 1000000007   

 

##### 제출답안 

```
import sys

input = sys.stdin.readline 

K, P, N = map(int, input().split())
num = 1000000007 

result = K 
for _ in range(N): 
    k = result % num 
    p = P % num 
    result = k * p % num 

print(result) 
```



