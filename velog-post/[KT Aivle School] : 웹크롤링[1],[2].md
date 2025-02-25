<h4 id="919---920--새로운분야인-웹크롤링의강의가-시작되었습니다">9/19 - 9/20 : 새로운분야인 웹크롤링의강의가 시작되었습니다</h4>
<blockquote>
<p>사실 웹개발 관련해서 관심이 많아서 html,css,javascript,Spring 다 공부를 해봤어서 강의 듣기전부터 기대가 되었습니다 ! </p>
</blockquote>
<p>Client (broswer) - 인터넷망 - Server (was)</p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/173bd5f2-0f88-4372-b77b-bf58f264c9c1/image.png" /></p>
<ul>
<li><p>C -&gt; I -&gt; S</p>
<pre><code>  (request)</code></pre></li>
<li><p>S -&gt; I -&gt; C </p>
<pre><code>  (response)</code></pre></li>
<li><p>url 가져오는 법 : dev tools 사용 (F12)        </p>
</li>
</ul>
<p>동적페이지든 정적페이지든 url에서 받아오는 첫 data는 html이다 </p>
<ul>
<li>웹페이지 URL에서 받아오는 data는 html이다 -&gt; 화면이 나와야 하니까 ! </li>
<li>그 이후 request(url) 후 response로 받는 data에따라 동적페이지 , 정적페이지로 나뉜다.</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/5e9c19fe-0ab0-49ce-844d-20cd21583b36/image.png" /></p>
<ul>
<li>data parsing : response 받은 data를 원하는 형태로 바꾸는 것 
response로 받아오는 data형태가 달라 동적페이지와 정적페이지는 데이터파싱 방법이 다르다.</li>
</ul>
<h4 id="동적페이지">동적페이지</h4>
<ul>
<li>새로고침할때 url이 변화가 일어나지 않는다. </li>
<li>response가 json format 이다. json은 string형태</li>
<li>받아온 json format을 list,dict -&gt; DF 형태로 파싱한다. </li>
</ul>
<h4 id="정적페이지">정적페이지</h4>
<ul>
<li>새로고침할때 url이 변화가 일어난다. </li>
<li>response가 html code 이다. html은 string형태</li>
<li>html은 태그형태로 있기때문에 json 보다 데이터파싱하기 어렵다.</li>
<li>html -&gt; bs4 (css-selector) -&gt; text(list ,dict) -&gt; DF 이런 과정으로 데이터파싱을 한다. </li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/6cedde13-3511-4309-a12a-972fc1cea0bc/image.png" /></p>
<ul>
<li>URL 구조
1) HTTP : 프로토콜 
cf) HTTPS : 안전성을 높인 프로토콜 , 암호화 복호화 과정이 있어야 하기때문에 보안에 강하다.
2) n.con : 도메인 </li>
</ul>