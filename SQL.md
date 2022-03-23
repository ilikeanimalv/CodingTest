# 프로그래머스 - SQL 코딩테스트 연습

## LEVEL 3 헤비 유저가 소유한 장소

### 문제
![헤비 유저가 소유한 장소1](https://user-images.githubusercontent.com/69181105/159736123-ceffb93c-6e14-4b78-8ae4-7ee0c269a55b.png)
![헤비 유저가 소유한 장소2](https://user-images.githubusercontent.com/69181105/159736133-55659b70-b439-45ad-837c-dc2cfe6e0ceb.png)

### 문제 요약

1. 헤비 유저는 **PLACES** 테이블에서 *HOST_ID*가 2개 이상 출력되는 *HOST_ID*임
  
2. 헤비 유저만 포함된 **PLACES** 테이블을 출력해야 함
  

### 문제 풀이

1. <u>서브쿼리</u>를 통해 헤비유저의 *HOST_ID*를 출력받음
  
2. 헤비유저의 테이블을 출력
  

### 코드

```sql
SELECT *
FROM PLACES
WHERE HOST_ID IN(
SELECT HOST_ID
FROM PLACES
GROUP BY HOST_ID
HAVING COUNT(*) >= 2);
```

### 코드 핵심사항

1. 중첩 서브쿼리의 활용(WHERE절 서브쿼리)

- 단일행 서브쿼리인 경우
  - 서브쿼리의 수행 결과가 오직 하나의 ROW만을 반환함
    
  - 단일행 비교 연산자를 사용(>, >=, <.<=,= 등)
    

```sql
# ex) 사원들의 평균 급여보다 더 많은 급여를 받는 사원을 검
WHERE SAL > (SELECT AVG(SAL) 
             FROM EMP);
```

- 다중행 서브쿼리인 경우
  
  - 서브쿼리의 수행 결과가 두 건 이상의 데이터를 반환함
    
  - 다중행 비교 연산자를 사용(IN, ANY, SOME, ALL, EXISTS 등)
    

```sql
# ex) 30번 소속 사원들 중 급여를 가장 많이 받는 사원보다 더 많은 급여를 받는 사람의 이름과 급여를 출력
SELECT  ENAME, SAL
  FROM  EMP
 WHERE  SAL > ALL ( SELECT  SAL
                      FROM  EMP
                     WHERE  DEPTNO = 30 );
```
