<p>_2025.07.01 _</p>
<h3 id="j-별칭-설정">$j 별칭 설정</h3>
<blockquote>
<p>원래 jQuery는 $인데 두 개 이상 jQuery로딩시 충돌방지를 위해 별칭으로 설정해놓으면 오류방지 <br /> <code>var $j = jQuery.noConflict();</code></p>
</blockquote>
<h3 id="html">HTML</h3>
<pre><code>&lt;input type=&quot;button&quot; value=&quot;작성 후 다음 페이지&quot; /&gt;
input과 같이 value를 사용시 버튼 안에 표시되는 글씨가 된다.</code></pre><input type="button" value="작성 후 다음 페이지" />

<pre><code>&lt;button&gt;작성 후 다음 페이지&lt;/button&gt; &lt;!-- 이렇게 --&gt;
같은 결과를 내는데 다른 표현
</code></pre><p><button>작성 후 다음 페이지</button> <!-- 이렇게 --></p>
<hr />
<table>
<thead>
<tr>
<th>개념</th>
<th>역할</th>
</tr>
</thead>
<tbody><tr>
<td><code>id=&quot;submitBtn&quot;</code></td>
<td>HTML에서 요소를 식별하는 <strong>속성(Attribute)</strong></td>
</tr>
<tr>
<td><code>document.getElementById(&quot;submitBtn&quot;)</code></td>
<td>자바스크립트로 그 요소를 가져오는 <strong>함수</strong></td>
</tr>
</tbody></table>
<h3 id="의존성-주입-어노테이션">의존성 주입 어노테이션</h3>
<pre><code>@Autowired
private BoardService boardService;
new를 사용하지않아도 Spring이 BoardService 타입의 객체를 찾아서 자동으로 넣어줌 </code></pre><h3 id="sqlsession">SqlSession</h3>
<p>MyBatis에서 SQL을 실행하기 위한 핵심 인터페이스입니다.
쉽게 말해, <strong>SQL을 DB에 보내는 &quot;직접적인 창구&quot;</strong>입니다.</p>