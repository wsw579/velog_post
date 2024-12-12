<blockquote>
<p>** SQL 시작 !
SQLD 자격증도있고 학교에서 SQL 수업도 듣고 공부도 했었는데 .....
조그 시간도 지나고 뭔가 제대로 공부한적은 없는 것 같아서 이번에 한 번 더 꼼꼼하게 집중해서 공부하려고 한다! ** 💪🏻</p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/693a7315-2089-418a-bac4-af7633408baf/image.png" /></p>
<ul>
<li><strong>Hostname (호스트네임):</strong> 내 로컬 주소 (예: <code>localhost</code>, <code>127.0.0.1</code>, 혹은 컴퓨터 이름). 접근하려는 서버의 네트워크 위치를 나타냄.</li>
<li><strong>Port (포트):</strong> 접근하려는 서버의 특정 서비스가 실행 중인 네트워크 포트 번호 (예: <code>3306</code>은 MySQL 기본 포트).</li>
<li><strong>Username (사용자 이름):</strong> 서버나 데이터베이스에 접근할 때 필요한 사용자 계정 이름.</li>
<li><strong>Schema (스키마):</strong> 데이터베이스의 구조를 정의하며, 데이터베이스 자체를 가리키는 용도로 사용되기도 함. (SQL 문맥에서 &quot;스키마&quot;는 테이블, 뷰, 인덱스 등 데이터베이스의 객체들을 포함하는 구조를 말함.)</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/60f09f26-cd0a-458a-b452-6cde7f4bd398/image.png" /></p>
<ul>
<li><strong>hrdb2024 클릭을 하고 실행시 . employee만 하면되고</strong></li>
<li><strong>그냥 쓸거면 다 써줘야한다.</strong></li>
</ul>
<p><strong>SQL에서 결측치를 다 제거 , merge , groupby 등 다 가능</strong></p>
<p>→ 이걸로 db만 공유하면 모든사람들이 같은 데이터를 공유할 수 있다.</p>
<p><strong>SQL은 시각화가 안된다 !</strong> </p>
<p><strong>MYSQL 은 Reverse diagram을 그려준다!</strong> </p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/ffa179cd-64e1-4a76-96ed-417b22555672/image.png" /></p>
<p><strong>MYSQL  , oracle , postage  - 리눅스 기반은 대소문자 구문 !</strong> </p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/7ac813c4-8655-4770-bd4c-0867c7bdef1d/image.png" /></p>
<p>1번을 처리하는데 쉽다. = Table Scan</p>
<p>전화번호부 처럼 ‘ㄱㄴㄷㄹ .. ‘ 이렇게 정렬되니까 처음부터 읽게되면 김씨인 사람을 찾는게 </p>
<p>더 쉽다. </p>
<h2 id="coalesce--vs--ifnull"><strong>COALESCE</strong>  VS  <strong>IFNULL</strong></h2>
<h3 id="주요-차이점-요약"><strong>주요 차이점 요약</strong></h3>
<table>
<thead>
<tr>
<th>구분</th>
<th>COALESCE</th>
<th>IFNULL</th>
</tr>
</thead>
<tbody><tr>
<td><strong>인자 수</strong></td>
<td>다수의 인자 처리 가능</td>
<td>두 개의 인자만 처리 가능</td>
</tr>
<tr>
<td><strong>SQL 표준 지원 여부</strong></td>
<td>SQL 표준 (모든 DBMS에서 지원)</td>
<td>SQL 표준 아님 (MySQL 등 지원)</td>
</tr>
<tr>
<td><strong>가독성 및 간단함</strong></td>
<td>다소 복잡한 상황에서 유용</td>
<td>간단한 <code>NULL</code> 대체에 적합</td>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
</tr>
</tbody></table>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/e2a375f7-8046-4805-9eda-0b910096a894/image.png" /></p>
<ul>
<li>salary는 물리적인값이기 때문에 별칭도 , salary도 사용가능 근데 다르게 적용됨</li>
<li>별칭으로 줄때가 우선순위가 더 높다</li>
</ul>