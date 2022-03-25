# Python 코딩테스트

## 구분 : 코테 Demo Test

### 문제
![1](https://user-images.githubusercontent.com/69181105/160065864-d41ec131-e41e-4453-89e4-bd636993300f.png)
![2](https://user-images.githubusercontent.com/69181105/160065869-31cc53bd-7ab9-4419-b13d-7bc4f59980a7.png)


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
