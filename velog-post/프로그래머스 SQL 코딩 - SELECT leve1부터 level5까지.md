<p><a href="https://school.programmers.co.kr/learn/courses/30/parts/17042">프로그래머스 SELECT 문제 바로가기</a></p>
<h1 id="select">SELECT</h1>
<h2 id="☑️-select-level-1">☑️ SELECT level 1</h2>
<h3 id="1-평균-일일-대여-요금">1. 평균 일일 대여 요금</h3>
<blockquote>
<pre><code>SELECT ROUND(AVG(DAILY_FEE)) AS AVERAGE_FEE
    FROM CAR_RENTAL_COMPANY_CAR
    WHERE CAR_TYPE = 'SUV'; ```</code></pre></blockquote>
<h3 id="2--과일로-만든-아이스크림">2.  과일로 만든 아이스크림</h3>
<blockquote>
<pre><code>SELECT f.FLAVOR
    FROM FIRST_HALF AS f
    JOIN ICECREAM_INFO AS i
        on f.FLAVOR = i.FLAVOR
    WHERE f.TOTAL_ORDER &gt; 3000  
        AND i.INGREDIENT_TYPE = 'fruit_based'
        AND f.FLAVOR IN ('strawberry' , 'melon')
    ORDER BY f.TOTAL_ORDER DESC ; ```</code></pre></blockquote>
<h3 id="3-흉부외과이거나-일반외과인-의사-목록-출력">3. 흉부외과이거나 일반외과인 의사 목록 출력</h3>
<blockquote>
<pre><code>SELECT DR_NAME , DR_ID , MCDP_CD , DATE_FORMAT(HIRE_YMD, '%Y-%m-%d') AS HIRE_YMD
FROM DOCTOR 
WHERE MCDP_CD IN('CS','GS')
ORDER BY  HIRE_YMD DESC , DR_NAME ASC ; ```</code></pre></blockquote>
<ul>
<li><strong>DATE_FORMAT(HIRE_YMD,'%Y-%m-%d')</strong></li>
<li><em><code>%Y</code>*</em>: 4자리 연도 (예: <code>2020</code>)</li>
<li><em><code>%m</code>*</em>: 2자리 월 (01~12, 예: <code>03</code> 또는 <code>11</code>)</li>
<li><em><code>%d</code>*</em>: 2자리 일 (01~31, 예: <code>01</code>, <code>15</code>)</li>
<li><em><code>%M</code>*</em>: 전체 월 이름 (예: <code>January</code>, <code>February</code>)</li>
<li><em><code>%D</code>*</em>: 일자에 대한 서수 (예: <code>1st</code>, <code>2nd</code>, <code>3rd</code>)</li>
</ul>
<h3 id="4-인기있는-아이스크림">4. 인기있는 아이스크림</h3>
<blockquote>
<pre><code>SELECT FLAVOR
FROM FIRST_HALF  
ORDER BY TOTAL_ORDER DESC , SHIPMENT_ID ASC ; </code></pre></blockquote>
<p>````</p>
<h3 id="5-강원도에-위치한-생산공장-목록-출력하기">5. 강원도에 위치한 생산공장 목록 출력하기</h3>
<blockquote>
<pre><code>SELECT FACTORY_ID, FACTORY_NAME , ADDRESS 
FROM FOOD_FACTORY 
WHERE ADDRESS LIKE '%강원도%'
ORDER BY FACTORY_ID ASC;</code></pre></blockquote>
<pre><code>
### 6. 12세 이하인 여자 환자 목록 출력하기 
&gt; ```
SELECT PT_NAME, PT_NO ,GEND_CD , AGE , IFNULL(TLNO, 'NONE') AS TLNO
FROM PATIENT
WHERE AGE &lt;= 12 AND GEND_CD = 'W'
ORDER BY AGE DESC , PT_NAME ASC ;</code></pre><ul>
<li>IFNULL 은 SELECT 절에서 </li>
</ul>
<h3 id="7-조건에-맞는-도서-리스트-출력하기">7. 조건에 맞는 도서 리스트 출력하기</h3>
<blockquote>
<pre><code>SELECT BOOK_ID, DATE_FORMAT(PUBLISHED_DATE,'%Y-%m-%d') AS PUBLISHED_DATE
FROM BOOK
WHERE PUBLISHED_DATE &gt;= '2021-01-01' AND PUBLISHED_DATE &lt;= '2021-12-31' 
AND CATEGORY ='인문'
ORDER BY PUBLISHED_DATE ASC ; </code></pre></blockquote>
<pre><code>
### 8. 조건에 부합하는 중고거래 댓글 조회하기 
&gt; ```
SELECT b.TITLE, b.BOARD_ID , r.REPLY_ID, r.WRITER_ID , r.CONTENTS, DATE_FORMAT(r.CREATED_DATE,'%Y-%m-%d') AS CREATED_DATE
FROM USED_GOODS_BOARD AS b
JOIN USED_GOODS_REPLY AS r 
ON b.BOARD_ID = r.BOARD_ID  
WHERE b.CREATED_DATE LIKE '2022-10%'
ORDER BY 6 , 1 ; </code></pre><ul>
<li><p>*<em>ORDER BY 6, 1  *</em>
SELECT 문에서 조회하려는 열 순서사용하면 더 간단하다 , ORDER BY default → ASC</p>
</li>
<li><p>** 2022년 10월에 작성된 조건문**
WHERE b.CREATED_DATE LIKE '2022-10%’
=   b.CREATED_DATE  ≥ ‘2022-10-01’ AND  b.CREATED_DATE  ≤ ‘2022-10-31’ =  b.CREATED_DATE  BETWEEN  ‘2022-10-01’ AND ‘2022-10-31’</p>
</li>
</ul>
<h3 id="9-모든-레코드-조회하기">9. 모든 레코드 조회하기</h3>
<blockquote>
<pre><code>SELECT ANIMAL_ID,ANIMAL_TYPE,DATETIME,INTAKE_CONDITION,NAME,SEX_UPON_INTAKE
FROM ANIMAL_INS
ORDER BY ANIMAL_ID ASC ; </code></pre></blockquote>
<pre><code>
### 10. 역순 정렬하기 
&gt; ```
SELECT NAME,DATETIME
FROM ANIMAL_INS 
ORDER BY ANIMAL_ID DESC ;</code></pre><h3 id="11아픈-동물-찾기">11.아픈 동물 찾기</h3>
<blockquote>
<pre><code>SELECT ANIMAL_ID,NAME
FROM ANIMAL_INS
WHERE INTAKE_CONDITION ='Sick'
ORDER BY 1 ;</code></pre></blockquote>
<pre><code>
### 12. 가장 큰 물고기 10마리 구하기 
&gt; ```
SELECT ID , LENGTH 
FROM FISH_INFO 
WHERE LENGTH IS NOT NULL 
ORDER BY LENGTH DESC , ID ASC 
LIMIT 10 ;</code></pre><ul>
<li>LIMIT  -- 자리는 마지막</li>
</ul>
<p>EX ) LIMIT 10 - 상위 10개만출력</p>
<h3 id="13-python-개발자-찾기">13. Python 개발자 찾기</h3>
<blockquote>
<pre><code>WHERE (SKILL_1 = 'Python' OR SKILL_2 = 'Python' OR SKILL_3 = 'Python')</code></pre></blockquote>
<pre><code>
- WHERE (SKILL_1 = 'Python' OR SKILL_2 = 'Python' OR SKILL_3 = 'Python')
= WHERE 'Python' IN (SKILL_1, SKILL_2, SKILL_3)

### 14. 어린 동물 찾기 
&gt; ```
SELECT ANIMAL_ID,NAME
FROM ANIMAL_INS 
WHERE INTAKE_CONDITION != 'Aged'
ORDER BY ANIMAL_ID ASC ;</code></pre><ul>
<li>WHERE INTAKE_CONDITION != 'Aged'
= WHERE NOT INTAKE_CONDITION = 'Aged'
= INTAKE_CONDITION NOT IN ('Aged')</li>
</ul>
<h3 id="15-동물의-아이디와-이름">15. 동물의 아이디와 이름</h3>
<blockquote>
<pre><code>SELECT ANIMAL_ID , NAME
FROM ANIMAL_INS
ORDER BY ANIMAL_ID ; </code></pre></blockquote>
<pre><code>
### 16. 여러 기준으로 정렬하기
&gt; ```
SELECT ANIMAL_ID , NAME    ,DATETIME
FROM ANIMAL_INS 
ORDER BY 2 , 3 DESC ; </code></pre><h3 id="17-상위-n개-레코드">17. 상위 n개 레코드</h3>
<blockquote>
<pre><code>SELECT NAME
FROM ANIMAL_INS 
ORDER BY DATETIME ASC
LIMIT 1;</code></pre></blockquote>
<pre><code>
- 집계함수는 SELECT / HAVING 절에만 사용 
→ WHERE절에는 사용할 수 없음 

### 18. 조건에 맞는 회원수 구하기 
&gt; ```
SELECT COUNT(USER_ID) AS USERS
FROM USER_INFO
WHERE JOINED LIKE '2021%' AND (AGE BETWEEN 20 AND 29) ;</code></pre><br />

<hr />
<br />


<h2 id="☑️-select-level-2">☑️ SELECT level 2</h2>
<h3 id="19-3월에-태어난-여성-회원-목록-출력하기">19. 3월에 태어난 여성 회원 목록 출력하기</h3>
<blockquote>
<pre><code>SELECT MEMBER_ID,MEMBER_NAME,GENDER,DATE_FORMAT(DATE_OF_BIRTH,'%Y-%m-%d') AS DATE_OF_BIRTH
FROM MEMBER_PROFILE
WHERE TLNO IS NOT NULL AND GENDER = 'W' AND MONTH(DATE_OF_BIRTH) = 3
ORDER BY 1;</code></pre></blockquote>
<pre><code>
- MONTH(DATE_OF_BIRTH) = 3
= WHERE DATE_OF_BIRTH LIKE '____-03-%';
= DATE_FORMAT(DATE_OF_BIRTH, '%m') = '03';

### 20. 재구매가 일어난 상품과 회원 리스트 구하기 
&gt; ```
SELECT USER_ID ,PRODUCT_ID
    FROM ONLINE_SALE
    GROUP BY USER_ID, PRODUCT_ID 
    HAVING COUNT(*) &gt; 1
    ORDER BY USER_ID , PRODUCT_ID DESC ;</code></pre><h3 id="21-업그레이드-된-아이템-구하기">21. 업그레이드 된 아이템 구하기</h3>
<blockquote>
<pre><code>SELECT i.ITEM_ID,i.ITEM_NAME,i.RARITY
FROM ITEM_INFO AS i
JOIN ITEM_TREE AS t
ON i.ITEM_ID = t.ITEM_ID
WHERE t.PARENT_ITEM_ID IN (
    SELECT ITEM_ID
    FROM ITEM_INFO
    WHERE RARITY = 'RARE'
)
ORDER BY i.ITEM_ID DESC;</code></pre></blockquote>
<pre><code>
- 서브쿼리 문
- 결과를 봤을땐 어렵지않은데 솔직히 문제만 봤을때 쿼리문을 생각하기 힘들었다 .. 

### 22. 조건에 맞는 개발자 찾기 
&gt; ```
SELECT ID, EMAIL, FIRST_NAME, LAST_NAME
FROM DEVELOPERS
WHERE (SKILL_CODE &amp;
(SELECT SUM(CODE) FROM SKILLCODES WHERE NAME IN ('Python', 'C#')) ) &gt; 0
ORDER BY 1;</code></pre><ul>
<li>맞는 구문인데 계속 에러가 나서 왜그런가 봤더니 
예제처럼 Python , C#이 고정된 값이 아니였다 즉, 
WHERE (SKILL_CODE &amp; 256) &gt; 0 OR (SKILL_CODE &amp; 1024) &gt; 0 조건을 이렇게 주면 안된다. </li>
<li>어떻게 풀어야할지 감이 안왔던 문제 .. </li>
</ul>
<h3 id="23-특정-물고리를-잡은-총-수-구하기">23. 특정 물고리를 잡은 총 수 구하기</h3>
<blockquote>
<pre><code>SELECT COUNT(i.FISH_TYPE) AS FISH_COUNT
FROM FISH_INFO AS i
JOIN FISH_NAME_INFO AS n
 ON i.FISH_TYPE = n.FISH_TYPE
WHERE n.FISH_NAME IN ('BASS', 'SNAPPER');</code></pre></blockquote>
<pre><code>
### 24. 부모의 형질을 모두 가지는 대장균 찾기 
&gt; ```
SELECT c.ID, c.GENOTYPE AS GENOTYPE , p.GENOTYPE AS PARENT_GENOTYPE
FROM ECOLI_DATA AS c
JOIN ECOLI_DATA AS p 
on c.PARENT_ID = p.ID
WHERE (c.GENOTYPE &amp; p.GENOTYPE) = p.GENOTYPE
ORDER BY 1; 

- self-join 예제 

## ☑️ SELECT level 3

### 25. 대장균들의 자식의 수 구하기 
&gt; ```
SELECT p.ID , IFNULL(SUM(p.ID = c.PARENT_ID), 0) AS CHILD_COUNT
FROM ECOLI_DATA AS p
LEFT JOIN ECOLI_DATA AS c
ON p.ID = c.PARENT_ID
GROUP BY p.ID 
ORDER BY 1;



## ☑️ SELECT level 4

### 서울에 위치한 식당 목록 출력하기 
&gt; ```
SELECT i.REST_ID, i.REST_NAME , i.FOOD_TYPE,i.FAVORITES    ,i.ADDRESS, ROUND(AVG(r.REVIEW_SCORE),2) AS SCORE 
FROM REST_INFO AS i
JOIN REST_REVIEW AS r 
on i.REST_ID = r.REST_ID
WHERE i.ADDRESS LIKE '서울%'
GROUP BY i.REST_ID, i.REST_NAME , i.FOOD_TYPE,i.FAVORITES,i.ADDRESS
ORDER BY SCORE DESC , i.FAVORITES DESC;</code></pre><h3 id="오프라인온라인-판매-데이터-통합하기">오프라인/온라인 판매 데이터 통합하기</h3>
<blockquote>
<pre><code>SELECT DATE_FORMAT(SALES_DATE,'%Y-%m-%d') AS SALES_DATE  , PRODUCT_ID, USER_ID,  SALES_AMOUNT
FROM ONLINE_SALE 
WHERE SALES_DATE LIKE '2022-03%'
UNION ALL
SELECT DATE_FORMAT(SALES_DATE,'%Y-%m-%d') AS SALES_DATE , PRODUCT_ID, NULL AS USER_ID, SALES_AMOUNT
FROM OFFLINE_SALE 
WHERE SALES_DATE LIKE '2022-03%'
ORDER BY 1 ,2 ,3 ;</code></pre></blockquote>
<ul>
<li>UNION ALL : 중복제거없이 합치기
  → JOIN 과 구분잘해서 사용하기 ! </li>
</ul>