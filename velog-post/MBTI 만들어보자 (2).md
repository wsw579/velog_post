<p>2025.06.30</p>
<ul>
<li>계속 프론트에서 오류나는데 후 ... 쉽지않다. 오류메세지가 뜨면 그거에 맞게 해결할텐데 내가원하는대로 기능하지않아서 ㅁrㄱㅁrㄱ 그래도 해야지 </li>
</ul>
<blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/6cb95e11-3c78-4498-996b-ea4cdc7e2bad/image.png" /> 1. 첫번째 오류  --&gt; 오른쪽 3번째를 선택했을때 선택한 대상만 색칠이되고싶은데 , 사진처럼 오른쪽 첫번째부터 3번째까지 색칠됨 
오류 이유 1. JSP 안에서 <label> 태그 안에 c:choose 태그를 직접 넣음 2. JSP 태그가 HTML class=&quot;...&quot; 속성 안에 들어가면 브라우저는 해석 불가능
3. 태그 안에 줄 바꿈, 공백, 조건부 class가 섞이면 class 전체가 깨짐
4. 그래서 라디오 3개 중 하나만 선택해도 나머지에도 같은 클래스가 중복으로 붙어버림</p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/e3e7b544-651f-4f8d-a968-47a06b745b51/image.png" /></p>
<blockquote>
<p>이제 2번을 설계중 
설계하면서 개념 빈거 다시 공부중 ... </p>
</blockquote>
<h3 id="jsp---controller--데이터-교환-흐름">JSP - Controller  데이터 교환 흐름</h3>
<p>✅ &quot;내가 JSP에서 method=&quot;post&quot;로 데이터를 보내면,
그 데이터를 받는 서버 쪽 URL에서는 그냥 아무 방식으로나 받아도 되는 건지,
post로 보내면 post로만 받아야 하는 건지&quot;
👉 보내는 쪽은 “나 데이터 보낼게요~ (POST로)”
👉 받는 쪽은 “나는 POST 방식의 요청만 받을 거야”</p>
<h3 id="httpservletrequest-request-와-locale-locale">HttpServletRequest request 와 Locale locale</h3>
<table>
<thead>
<tr>
<th>항목</th>
<th><code>HttpServletRequest request</code></th>
<th><code>Locale locale</code></th>
</tr>
</thead>
<tbody><tr>
<td>목적</td>
<td>사용자의 HTTP 요청 전체 접근</td>
<td>사용자의 언어/국가 정보 확인</td>
</tr>
<tr>
<td>타입</td>
<td>Java EE 표준 Servlet 객체</td>
<td>Java 표준 지역(locale) 객체</td>
</tr>
<tr>
<td>대표용도</td>
<td>파라미터 꺼내기 (<code>getParameter</code>)</td>
<td>다국어 처리, 메시지 번역 등</td>
</tr>
<tr>
<td>직접 입력</td>
<td>거의 항상 필요</td>
<td>보통 <code>MessageSource</code> 쓸 때만</td>
</tr>
</tbody></table>
<h3 id="parameter--new-객체">Parameter / new 객체</h3>
<p> ✅ 데이터 바인딩이란?
<strong>HTML form에 입력된 데이터(name 속성 기반)</strong>를
Java 객체(MbtiVo)의 필드에 자동으로 넣어주는 Spring 기능이야.</p>
<table>
<thead>
<tr>
<th>방식</th>
<th>특징</th>
</tr>
</thead>
<tbody><tr>
<td><code>@RequestParam</code>, <code>HttpServletRequest</code></td>
<td>값 하나하나 수동 처리</td>
</tr>
<tr>
<td><code>MbtiVo mbtiVo</code></td>
<td>Spring이 자동으로 객체 생성 + 값 주입까지 다 해줌 (데이터 바인딩)</td>
</tr>
</tbody></table>