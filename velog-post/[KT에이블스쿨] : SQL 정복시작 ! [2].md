<ul>
<li>직원의 사번을 알아야 어떤 직원이 휴가를 간지 알수있으니까</li>
</ul>
<p>→ 직원테이블 — 휴가테이블 </p>
<ul>
<li>외래키 : 다른테이블에서  온 키</li>
<li>참조키 : 다른테이블에서 온 키인데 참조를 위한 키
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/509d4252-851f-4e98-87e3-c7f66c921ede/image.png" /></li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/54625455-7866-47d3-8a7b-c9c97509ca95/image.png" /></p>
<p>o 이 있으면 zero or more </p>
<ul>
<li>휴가는 안가거나 여러번 갈 수 있다.</li>
</ul>
<p>만약 무조건 휴가를 가야한다고 하면 one or more로 바꾸기</p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/c3f125f7-68af-46ca-9e0e-86d5dec591de/image.png" /></p>
<p>부서에는 사번이 있어야 직원을 알 수 있으니까 연결</p>
<ul>
<li>위에는 무조건 부서코드가 하나 있어야한다</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/e378ab5e-0c9f-4195-9e35-75cee8353731/image.png" /></p>
<ul>
<li>이거는 아직 부서를 배정받지못할수도있다는 조건 zero or one </li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/248a91cc-d063-4d2c-b92f-7e54b7f2dddf/image.png" /></p>
<ul>
<li>지금 별명테이블로 따로 만든게 정규화</li>
<li>별명을 속성으로 넣으면 별명이 없는사원은 NULL값을 가지게 되므로 정규화를 해준다</li>
<li>여기서 별명테이블을 JOIN하고 ,  NULL값을 가진다고 생각하고 다시 넣어주는게 역정규화라고 한다.</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/fd9ec8ef-9a0b-4503-8ee4-1c6d3f5611d4/image.png" />
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/120f7879-9659-4545-8983-aba5dd8136cc/image.png" /></p>
<ul>
<li>대리키 , 사번 ,  동호회코드가 있지만 동호회가입번호가 PK를 대신한다.</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/7dbee053-4514-43b1-824a-0b3a04adc469/image.png" /></p>
<p><strong>외래키(Foreign Key)는 다른 테이블의 기본키(Primary Key, PK)를 참조하는 키.</strong></p>
<p><strong>외래키를 사용하면, 두 테이블 간에 참조 무결성(Referential Integrity)을 유지할 수 있다</strong></p>
<h2 id="정규형">정규형</h2>
<p>1차 정규형 = 원자성 </p>
<p>2차정규형 = <strong>복합키가진 테이블에서</strong> 테이블에 중복된 값을 갖는 컬럼이 있으면 안된다.</p>
<p>3차정규화 : 비 기본키 속성이 다른 비 기본키 속성에 종속되지않도록한다.</p>
<p>즉, 부서코드를 사용할때마다 부서이름도 실행되면 안된다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/13b33c41-dc81-482b-9c85-d84730abebad/image.png" /></p>
<blockquote>
<p>3차 정규화 후 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/af7b09e3-1355-4fbf-8394-6de744bf4b94/image.png" /></p>
</blockquote>
<h2 id="역정규화">역정규화</h2>
<ul>
<li>데이터를 중복저장해서 복잡한 쿼리구조를 단순화함 근데 이에따른 책임을 져야한다.</li>
<li>→  속도&amp;성능때문에 하는것이다.</li>
<li>단점 1) 중복저장으로 저장공간증가됨 2) 중복으로 데이터 일관성 유지 어려움 3) 데이터 추가,수정,삭제 힘들어짐 ( 왜냐하면 동일한 데이터가 여기저기 저장되어있으니까)</li>
</ul>
<br /> 

<h2 id="delete--truncate">DELETE / TRUNCATE</h2>
<h3 id="주요-차이점-비교"><strong>주요 차이점 비교</strong></h3>
<table>
<thead>
<tr>
<th>특징</th>
<th>DELETE</th>
<th>TRUNCATE</th>
</tr>
</thead>
<tbody><tr>
<td><strong>조건 사용 가능</strong></td>
<td>가능 (<code>WHERE</code> 절 지원)</td>
<td>불가능 (전체 삭제만 가능)</td>
</tr>
<tr>
<td><strong>트랜잭션 지원</strong></td>
<td>지원 (ROLLBACK 가능)</td>
<td>제한적 (복구 불가)</td>
</tr>
<tr>
<td><strong>속도</strong></td>
<td>상대적으로 느림</td>
<td>매우 빠름</td>
</tr>
<tr>
<td><strong>AUTO_INCREMENT</strong></td>
<td>초기화되지 않음</td>
<td>초기화됨</td>
</tr>
<tr>
<td><strong>사용 제한</strong></td>
<td>제약 없음</td>
<td>외래 키 제약이 있으면 실행 불가</td>
</tr>
</tbody></table>
<h2 id="집계함수">집계함수</h2>
<ul>
<li>행으로만 집계할 수 있다.</li>
<li><strong>집계함수는 NULL 값을 무시한다.</strong></li>
<li>딱! 하나 count(<em>) *</em>NULL 값을 무시하지않는다.**</li>
</ul>
<p>avg → 100 ,100 , 100 ,100 , NULL = NULL 이 맞다 NULL 의 값은 모르니까 </p>
<p>근데 NULL 를 없는걸로 치고 합계를 400로낸다 ,  그래서 400/4 = 100이 평균이 된다. </p>
<p>따라서 답은 나오지만 우리가 예상했던 값(현실적인계산)이 안나올 수 있다. </p>
<ul>
<li><p><strong>QnA ) salary에 모두 null값만 들어가있으면 해당 행은 ?</strong></p>
<p>  <strong>salary 테이블에 null값만 있으면 집계결과도 null</strong></p>
</li>
</ul>
<h2 id="join"><strong>JOIN</strong></h2>
<ul>
<li><strong>INNER JOIN : 중간 겹치는것만 , ‘ 부분은 다 누락</strong></li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/5622e417-06fd-42f7-965c-b98d3e96398c/image.png" /></p>
<ul>
<li><strong>OUTER JOIN → 1) LEFT 2) RIGHT 3) FULL 3가지 존재</strong></li>
</ul>
<p><strong>1) LEFT</strong>
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/b5b661cf-4d4e-4f47-a736-909856532adc/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/6df6aba1-16bc-4833-927d-fcfecd4f581b/image.png" /></p>
<ul>
<li><strong>SELF JOIN</strong></li>
</ul>
<p><strong>직원 테이블에 관리자 컬럼이 존재하는 경우</strong></p>
<p><strong>직원 정보와 관리자의 전화번호를 함께 출력하고 싶으면 from 과 동일한 테이블을 join하기</strong> </p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/e61c0553-48e7-417f-a164-731b446fcb3c/image.png" /></p>
<ul>
<li><strong>직원테이블 셀프참조 —&gt; 관리자 컬럼 생성</strong></li>
</ul>
<p>남녀별 1등급여 사람 구현</p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/2d41636b-9003-4f3a-af9d-b63cd17fb147/image.png" /></p>
<ul>
<li><strong>QnA ) ROW_NUMBER를 사용하면 salary가 동일한 사람들의 순위는 어떤 기준으로 순위가 매겨지나요?</strong></li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/f0a3137a-f101-4643-af00-98484f894359/image.png" /></p>
<ul>
<li><strong>이렇게 명시적으로 기준을 주지않으면 , mysql 이 알아서 정렬한다.</strong></li>
</ul>
<p><strong>쿼신의 쿼리를 모방해보는것이 제일 실력을 빨리 늘릴 수 있다.</strong></p>
<p><strong>null값만 가장 아래에 보고 싶으면 order by duration 하면 된다.</strong></p>
<pre><code>SELECT e.emp_name , e.emp_id , e.dept_id , e.hire_date
FROM employee AS e   # 부모 -&gt; 자식 
INNER JOIN vacation AS v ON e.emp_id= v.emp_id
WHERE e.retire_date IS NULL;</code></pre><h3 id="두-쿼리의-차이점"><strong>두 쿼리의 차이점</strong></h3>
<table>
<thead>
<tr>
<th>구분</th>
<th>첫 번째 쿼리 (<code>employee</code> 기준)</th>
<th>두 번째 쿼리 (<code>vacation</code> 기준)</th>
</tr>
</thead>
<tbody><tr>
<td><strong>기준 테이블</strong></td>
<td><code>employee</code></td>
<td><code>vacation</code></td>
</tr>
<tr>
<td><strong>주된 관심 데이터</strong></td>
<td>직원 정보</td>
<td>휴가 데이터</td>
</tr>
<tr>
<td><strong>조인 방식</strong></td>
<td>직원 중에서 휴가 데이터를 가진 직원만 조회</td>
<td>휴가 데이터 중에서 관련 직원 정보 추가 조회</td>
</tr>
<tr>
<td><strong>의미적 차이</strong></td>
<td>직원 데이터 중심으로 휴가 여부 확인</td>
<td>휴가 데이터 중심으로 관련 직원 정보 확인</td>
</tr>
<tr>
<td><strong>사용 사례</strong></td>
<td>직원 정보를 분석하거나 필터링이 필요할 때</td>
<td>휴가 데이터를 분석하거나 직원의 정보를 추가할 때</td>
</tr>
</tbody></table>
<p><strong>인라인 뷰</strong>(Inline View)는 서브쿼리의 결과를 임시 테이블처럼 사용하여 상위 쿼리에서 참조할 수 있도록 하는 방식입니다. 이 용어는 주로 서브쿼리가 <code>FROM</code> 절에 포함될 때 사용됩니다.</p>