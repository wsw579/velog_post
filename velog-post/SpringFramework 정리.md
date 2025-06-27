<h3 id="ajax-방식과--form-submit-방식">AJAX 방식과 / form submit 방식</h3>
<blockquote>
<p><strong>✅ AJAX 방식과 ✅ form submit 방식은 웹 애플리케이션에서 데이터를 서버로 전송하는 대표적인 두 가지 방식인데, 동작 흐름과 사용자 경험(UX) 측면에서 큰 차이가 있다.</strong></p>
</blockquote>
<p>즉, 비동기와 동기의 차이이자 
*<em>화면 전환 차이 *</em>
form은 한 번 요청하면 페이지 전체가 서버에서 새로 만들어져서 오고,
AJAX는 요청한 데이터만 받아와서 자바스크립트가 현재 페이지 일부만 변경 , 
*<em>Form Submit (동기) AJAX (비동기) 요청방식 차이 *</em>
HTML form의 action 속성에 따라 전체 페이지 전송<br />JavaScript가 fetch, XMLHttpRequest로 요청</p>
<p>AJAX (비동기 통신 기술 개념)
 ├── XMLHttpRequest (예전 방식)
 ├── jQuery.ajax() (중간 시대)
 └── fetch() ✅ (최신, 기본 내장 방식)</p>
<h3 id="commonutil">CommonUtil</h3>
<blockquote>
<p>*<em>CommonUtil은 &quot;공통 유틸리티 기능을 담은 클래스&quot;
말 그대로 여러 컨트롤러나 서비스 등에서 공통적으로 사용하는 기능들을 모아둔 &quot;도구 상자&quot; 같은 역할 *</em></p>
</blockquote>
<table>
<thead>
<tr>
<th>구분</th>
<th>설명</th>
</tr>
</thead>
<tbody><tr>
<td><code>BoardVo</code></td>
<td>데이터를 담는 객체 (VO/DTO)</td>
</tr>
<tr>
<td><code>CommonUtil</code></td>
<td>자주 쓰이는 기능을 묶은 유틸리티 클래스 (ex: JSON 변환, 날짜 포맷 등)</td>
</tr>
<tr>
<td><code>Controller</code></td>
<td>요청 처리 담당 (비즈니스 흐름 조정)</td>
</tr>
</tbody></table>
<h3 id="el표현식">EL표현식</h3>
<blockquote>
<p>EL (Expression Language)은 <strong>JSP(Java Server Pages)</strong>에서
서버에서 넘겨준 값을 화면에 표시할 때 사용하는 표현식.</p>
</blockquote>
<pre><code>&lt;p&gt;안녕하세요, ${user.name}님&lt;/p&gt;
${} 안에 변수명을 쓰면, 서버에서 전달한 값을 출력해줌

예: request.setAttribute(&quot;user&quot;, new User(&quot;홍길동&quot;));</code></pre><h3 id="게시글-수정시-get--post-구성">게시글 수정시 GET / POST 구성</h3>
<p>@RequestMapping(value = &quot;/board/boardUpdateAction.do&quot;, method = RequestMethod.POST)
@ResponseBody
public String boardUpdateAction(Locale locale, BoardVo boardVo) throws Exception {
    int resultCnt = boardService.boardUpdate(boardVo);  // 여기가 핵심
    ...
}</p>