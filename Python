# Python 코딩테스트

## 구분 : 코테 Demo Test

### 문제

![](file://C:\Users\Lee\AppData\Roaming\marktext\images\2022-03-25-15-10-10-image.png?msec=1648188610536)

![](file://C:\Users\Lee\AppData\Roaming\marktext\images\2022-03-25-15-10-37-image.png?msec=1648188637722)

### 문제 요약

3개의 x,y 좌표가 주어졌을 때, 직사각형을 이루는 나머지 1개의 x,y좌표를 구하기

### 문제 풀이

count 함수를 이용, 나머지 1개의 좌표를 찾기

### 코드

```python
def solution(v):
    x=[]
    y=[]
    for i in v:
        x.append(i[0])
        y.append(i[1])
    
    #count(n번째)==1 이면 i를 출력
    
    for n in range (0,3):
        if x.count(x[n])==1:
            xcode=x[n]
        if y.count(y[n])==1:
            ycode=y[n]
        
    answer = [xcode,ycode] 
    return answer
```
