<h3 id="jpa-vs-mybatis">JPA vs Mybatis</h3>
<blockquote>
<p><strong>MyBatis의 Mapper    SQL을 직접 작성해서 Java 코드와 연결해주는 SQL 매핑 레이어
JPA의 Entity    Java 객체를 DB 테이블과 자동으로 매핑해주는 ORM의 핵심 클래스
즉, MyBatis는 SQL 중심, JPA는 객체 중심</strong></p>
</blockquote>
<h3 id="배우지-않았던-개념-mapper">배우지 않았던 개념 Mapper</h3>
<blockquote>
<p>**🔷 Mapper란?
👉 SQL 쿼리를 Java 메서드와 매핑(연결) 해주는 구성
MyBatis에서는 XML 파일(예: BoardMapper.xml)이나 인터페이스(Java 파일)로 정의됩니다. <br />
✅ Mapper의 주요 역할
역할    설명</p>
</blockquote>
<ol>
<li>SQL 정의    SELECT, INSERT, UPDATE, DELETE 같은 SQL문 작성</li>
<li>Java 메서드와 연결    DAO나 Service에서 메서드 호출 시 해당 SQL 실행</li>
<li>VO와 결과 매핑    쿼리 결과를 Java 객체(VO, DTO 등)로 자동 변환 <br /><br />🔹 예시: XML 기반 Mapper <pre><code>// BoardMapper.xml
&lt;mapper namespace=&quot;board&quot;&gt; 
 &lt;select id=&quot;selectBoardList&quot; resultType=&quot;BoardVo&quot;&gt;
     SELECT * FROM BOARD
 &lt;/select&gt; 
&lt;/mapper&gt; 
아래 메서드와 연결됩니다 
// BoardDao.java
List&lt;BoardVo&gt; selectBoardList(); **
</code></pre></li>
</ol>
<h3 id="post-방식이지만-responsebody를-썼느냐-안-썼느냐--차이">POST 방식이지만, @ResponseBody를 썼느냐 안 썼느냐  차이</h3>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/c43bf557-c008-44da-812e-696f8805bfe1/image.png" /></p>
<table>
<thead>
<tr>
<th>항목</th>
<th><code>@ResponseBody</code> 사용 (<code>boardWriteAction</code>)</th>
<th>미사용 (<code>deleteChecked</code>)</th>
</tr>
</thead>
<tbody><tr>
<td>목적</td>
<td><strong>AJAX 요청</strong> 응답</td>
<td><strong>폼 submit</strong> 이후 리다이렉트</td>
</tr>
<tr>
<td>반환값</td>
<td><strong>JSON (또는 문자열)</strong> 등 <strong>데이터 자체</strong></td>
<td><strong>뷰 이름 또는 리다이렉트 경로</strong></td>
</tr>
<tr>
<td>ViewResolver 작동</td>
<td>❌ 안 함 (데이터만 응답)</td>
<td>✅ 동작해서 view 혹은 redirect 처리</td>
</tr>
<tr>
<td>호출방식</td>
<td>JS의 <code>$j.ajax()</code> 같은 비동기 요청</td>
<td>form <code>submit</code> 같은 일반 요청</td>
</tr>
</tbody></table>
<blockquote>
<p><strong>🧠 왜 두 방식이 나뉘는가?
boardWriteAction은 JS에서 alert 띄우고, 응답값에 따라 동적으로 행동하려고 비동기 처리
deleteChecked는 굳이 JS로 응답 처리 안 하고, 삭제 후 바로 리스트 페이지로 이동하는 게 목적</strong></p>
</blockquote>
<blockquote>
<p><strong>🔁 정리
체크박스 선택 후 &quot;선택삭제&quot; 클릭 → 목록 새로고침    redirect: 방식 사용
삭제 후 메시지만 alert로 띄우고, 화면 유지하고 싶음    @ResponseBody + AJAX</strong></p>
</blockquote>
<blockquote>
<p>🚨 <strong>WARN : org.springframework.web.servlet.PageNotFound - No mapping found for HTTP request with URI [/board/deleteChecked.do] in DispatcherServlet with name 'appServlet'</strong> <br /> &gt; Spring MVC의 DispatcherServlet이 /board/deleteChecked.do 경로로 들어온 요청에 대해 해당 URL과 매핑된 컨트롤러 메서드(@RequestMapping)가 없다는 뜻입니다. <br /> <br />✅ <strong>자주 발생하는 원인과 해결 방법</strong>
컨트롤러에 해당 URL이 없음 -&gt; 실제로 경로가 잘못설정되어있었음<br /> *<em>@RequestMapping(value = &quot;/board/deleteChecked.do&quot;, method =RequestMethod.POST)
public String deleteChecked(@RequestParam(value = &quot;boardNums&quot;, required = false) List boardNums) *</em> </p>
</blockquote>