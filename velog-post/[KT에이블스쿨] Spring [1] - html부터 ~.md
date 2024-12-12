<p><a href="https://roadmap.sh/">개발자로드맵</a>  :  공부계획 , 방향잡기 , 면접소스얻기 좋을듯 하다 </p>
<p><a href="https://www.freecodecamp.org/">free code camp</a> : → 단계별 공부 사이트 ! 완료시 수료증발급 - linkedlist에 사용가능 ! 
<strong>프론트엔드</strong> </p>
<ul>
<li>svelte :  프론트엔드 개발을 쉽게 할 수 있는 tool , 요즘 뜨는 기술 ✨</li>
<li>Electron : 웹 기술(HTML, CSS, JavaScript)을 사용해 데스크톱 애플리케이션을 제작할 수 있게 함 ( EX) visual studio code , Notion , slack 등 )</li>
</ul>
<p><strong>백엔드</strong></p>
<ul>
<li>web개발을 위해선 Javascript ,GO 언어가 유리하다.</li>
<li>Postgre SQL이 뜨는중 ! —&gt; 확장성이 좋음</li>
</ul>
<hr />
<h1 id="spring"><strong>Spring</strong></h1>
<h3 id="1-인터넷">1. 인터넷</h3>
<p>인터넷은 전 세계의 컴퓨터와 네트워크를 연결해 정보를 교환하고, </p>
<p>다양한 서비스를 제공하는 거대한 네트워크입니다. </p>
<p>TCP/IP 프로토콜을 기반으로 동작하며, </p>
<p>라우터, 모뎀, 서버, DNS 등의 구성 요소가 협력하여 </p>
<p>사용자에게 연결성과 서비스를 제공합니다.</p>
<h3 id="2-이더넷">2. 이더넷</h3>
<p>이더넷은 네트워크의 가장 기본적인 물리적/데이터 링크 계층에서 동작하며, 데이터를 실제로 전송하는 기반 기술이다. IP, TCP, HTTP와 같은 상위 계층의 프로토콜은 모두 이더넷을 통해 데이터를 전달.  </p>
<p>따라서 이더넷은 네트워크 통신에서 가장 아래에 위치하여 상위 계층의 데이터 전송을 물리적으로 지원합니다.</p>
<p><strong>이더넷은 &quot;데이터를 실어나르는 도로&quot;,</strong> </p>
<p><strong>IP는 &quot;목적지를 찾는 지도&quot;,</strong> </p>
<p><strong>TCP는 &quot;물건을 안전하게 포장&quot;,</strong></p>
<p> <strong>HTTP는 &quot;사용자 요청을 전달하는 우편 서비스&quot; 같은 역할</strong></p>
<p><strong>2- 1.  네트워크의 계층적 구조 (OSI 7계층)</strong></p>
<ul>
<li><p><strong>물리 계층 (1계층)</strong>: 데이터를 전기 신호나 광신호 등으로 변환하여 실제 전송 (→ 이더넷이 데이터를 신호로 변환)</p>
</li>
<li><p><strong>데이터 링크 계층 (2계층)</strong>: 장치 간 데이터 전송 , 물리적 주소(MAC 주소)를 이용한 통신 관리.</p>
<p>  (→  이더넷은 프레임 단위로 데이터를 전송하고 MAC 주소를 사용해 장치를 식별)</p>
</li>
<li><p><strong>네트워크 계층 (3계층)</strong>: IP 주소를 사용해 데이터가 여러 네트워크를 경유해 목적지에 도달하도록 경로 설정.</p>
</li>
<li><p><strong>전송 계층 (4계층)</strong>: TCP/UDP를 사용해 데이터 전송을 신뢰성 있게 관리.</p>
</li>
<li><p><strong>세션/표현/응용 계층 (5~7계층)</strong>: HTTP와 같은 애플리케이션 레벨 프로토콜을 통해 사용자 요청 처리.</p>
</li>
</ul>
<p><strong>2-2. TCP/IP : 통신 , 인터넷을 이용하기위한 프로토콜</strong> </p>
<p>논리적 주소 : ipv4 </p>
<p>물리적주소  : mac </p>
<p><strong>2-3. 라우팅</strong> </p>
<p>네트워크에서 데이터 패킷이 출발지에서 목적지까지 가장 적합한 경로 찾아가는 과정 </p>
<p>ex ) 내 컴퓨터 → 네이버로 가는길 </p>
<p><strong>이더넷과 상위 프로토콜의 관계</strong></p>
<ul>
<li><strong>이더넷</strong>: 물리적인 데이터 전송과 MAC 주소 기반의 근거리 통신을 담당.</li>
<li><strong>IP (Internet Protocol)</strong>: 네트워크 계층으로, 전 세계적으로 유일한 IP 주소를 사용해 데이터를 전달.</li>
<li><strong>TCP (Transmission Control Protocol)</strong>: 전송 계층으로, 데이터의 신뢰성과 순서를 보장.</li>
<li><strong>HTTP (HyperText Transfer Protocol)</strong>: 애플리케이션 계층으로, 웹 브라우저와 서버 간의 데이터 요청/응답 관리.</li>
</ul>
<h3 id="프레임과-패킷이란-"><strong>프레임과 패킷이란 ?!?</strong></h3>
<table>
<thead>
<tr>
<th><strong>구분</strong></th>
<th><strong>프레임</strong></th>
<th><strong>패킷</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong>계층</strong></td>
<td>데이터 링크 계층(2계층)</td>
<td>네트워크 계층(3계층)</td>
</tr>
<tr>
<td><strong>범위</strong></td>
<td>동일 네트워크(LAN) 내에서 데이터 전송.</td>
<td>네트워크 간 데이터 전송.</td>
</tr>
<tr>
<td><strong>주소</strong></td>
<td>MAC 주소(출발지와 목적지의 물리적 주소) 사용.</td>
<td>IP 주소(출발지와 목적지의 논리적 주소) 사용.</td>
</tr>
<tr>
<td><strong>구조</strong></td>
<td>헤더 + 데이터 + 트레일러</td>
<td>헤더 + 데이터</td>
</tr>
<tr>
<td><strong>역할</strong></td>
<td>물리적 데이터 전달 및 오류 검출.</td>
<td>네트워크 간 데이터 전달.</td>
</tr>
<tr>
<td>- <strong>LAN(Local Area Network)</strong>: 하나의 스위치 또는 브리지에 연결된 장치들이 있는 네트워크.</td>
<td></td>
<td></td>
</tr>
<tr>
<td>- <strong>패킷</strong>은 <strong>네트워크 계층(3계층)</strong>에서 동작하며, <strong>다른 네트워크(LAN 또는 WAN)</strong> 간 데이터를 전송합니다.</td>
<td></td>
<td></td>
</tr>
<tr>
<td>- <strong>패킷은 IP 주소</strong>(논리 주소)를 사용해 송신자와 수신자를 식별합니다.</td>
<td></td>
<td></td>
</tr>
<tr>
<td>- <strong>네트워크 간 통신이란?</strong></td>
<td></td>
<td></td>
</tr>
<tr>
<td>- 라우터(Router)를 통해 하나의 네트워크에서 다른 네트워크로 데이터가 전달되는 것.</td>
<td></td>
<td></td>
</tr>
</tbody></table>
<ul>
<li><strong>데이터 흐름 예시</strong></li>
</ul>
<ol>
<li>사용자가 웹 브라우저에서 <code>www.example.com</code>을 요청 (HTTP).</li>
<li>요청 데이터는 TCP를 통해 전송 신뢰성을 확보.</li>
<li>IP는 패킷을 생성하여 라우터를 통해 경로를 설정.</li>
<li>패킷은 이더넷 프레임에 캡슐화되어 케이블을 통해 물리적으로 전송.</li>
</ol>
<hr />
<p><strong>컴퓨터가 인터넷을 하기위해선 ip , 응용프로그램으로 인터넷을 하기위해선 port가 필요하다 .</strong></p>
<blockquote>
<p>응용프로그램</p>
</blockquote>
<table>
<thead>
<tr>
<th><strong>구분</strong></th>
<th><strong>응용 프로그램</strong></th>
<th><strong>비응용 프로그램</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong>목적</strong></td>
<td>사용자의 작업을 수행 (예: 웹 브라우징, 문서 작성)</td>
<td>시스템 운영 및 하드웨어 관리 (예: 운영 체제, 드라이버)</td>
</tr>
<tr>
<td><strong>사용자 인터페이스</strong></td>
<td>존재 (사용자가 직접 상호작용)</td>
<td>없음 (사용자와 상호작용하지 않음)</td>
</tr>
<tr>
<td><strong>실행 주체</strong></td>
<td>사용자가 직접 실행</td>
<td>자동으로 백그라운드에서 실행</td>
</tr>
<tr>
<td><strong>예시</strong></td>
<td>Microsoft Word, Chrome, 게임</td>
<td>Windows, Linux, 프린터 드라이버</td>
</tr>
</tbody></table>
<hr />
<br />

<h3 id="3-server-답변--respense------client-요청--request-">3. Server (답변 : respense)  &lt; ———— &gt;  client (요청 : request )</h3>
<p>web에서 데이터를 요청, 답변하는것을 web server , web client 라고한다.</p>
<p>web client → html 문서를 받는다 → html 을 눈에 보이게 한다 = 렌더링 : 브라우저가 눈에 보이게함 </p>
<p>HTTP : 프로토콜 , 인터넷에 연결해서 통신이 된다는 것을 기저에 두고 웹문서를 주고받는다 </p>
<p>→  표로 정리 </p>
<table>
<thead>
<tr>
<th>계층별 프로토콜</th>
</tr>
</thead>
<tbody><tr>
<td>HTTP</td>
</tr>
<tr>
<td>TCP</td>
</tr>
<tr>
<td>IP</td>
</tr>
<tr>
<td>Ethernet</td>
</tr>
</tbody></table>
<p>ip 주소 231.117.1.36 → 너무길다 → 도메인 domain name 을 사용 ( 네이버 같이) </p>
<p>→ 이때 필요한 <strong>DNS</strong> </p>
<p><strong>DNS</strong> :  &quot;Domain Name System&quot;의 약자로, <strong>도메인 이름</strong>(예: <a href="http://www.google.com)%EC%9D%84">www.google.com)을</a> <strong>IP 주소</strong>(예: 142.250.72.68)로 변환하는 시스템입니다.
→ 사용자의 요청을 계층적으로 처리해 데이터를 빠르고 안정적으로 전달</p>
<p>네이버 서버에 도착</p>
<ul>
<li>80 port 라고 하면 일반적으로 web 서버라고 한다. ( http )</li>
<li>443 port   (https)</li>
</ul>
<h3 id="well---known-port"><strong>well - known port</strong></h3>
<ul>
<li>잘 알려진 port</li>
<li>22 port :  시큐어 셀 같은</li>
<li>53 port :  DNS  제공 서버</li>
<li>3306 : Mysql 제공 서버 : 등록된 포트</li>
</ul>
<p>HTML문서를 요청할때 방법 (1. get 2. post ) </p>
<ol>
<li>get을사용해서 request하면 → 주소에 request&amp;response 모든 내용들이 보인다</li>
<li>post </li>
</ol>
<p><strong>—&gt;  방법의 차이만 있지  둘 다  문서요청이라는 목적은 동일하다</strong> </p>
<p>response :  200 : 송신완료 /  400 : error  </p>
<h3 id="4-dhtml---동적-html-">4. DHTML ( = 동적 HTML )</h3>
<p>DHTML은 초기에는 <strong>인터넷 익스플로러</strong>와 <strong>넷스케이프 브라우저</strong>에 맞춰 개발된 기능들이었지만, </p>
<p>이후 <strong>AJAX</strong>(Asynchronous JavaScript and XML)와 <strong>HTML5</strong>의 발전으로 인해 동적인 웹 페이지 구현이 더욱 용이해짐.</p>
<p>오늘날 대부분의 동적 웹 페이지는 <strong>React</strong>, <strong>Vue</strong>, <strong>Angular</strong>와 같은 현대적인 JavaScript 프레임워크를 통해 구현.</p>
<ul>
<li>DHTML은 예전의 기술 용어였지만, 현재 웹 개발에서는 주로 <strong>동적 웹 페이지</strong>나 <strong>클라이언트 사이드 스크립팅</strong>으로 발전된 형태로 사용.</li>
<li><strong>클라이언트 사이드 스크립팅</strong>은 서버와의 상호작용 없이 <strong>웹페이지를 동적으로 제어</strong>하는 방식</li>
</ul>
<hr />
<p>웹 표준 &amp; 마크업언어 </p>
<p>표준화단체 </p>
<ul>
<li>W3C : 웹사이트 구성하는 html( 구조 ex) 웹툰으로 갈 수 있는 요소가 있어 , 콘텐츠 ), css(모양 , 배치 ), js(동적 - 가만히 있으면 차단해야하는 ui , 계속 변하는 내용)등에대한 규정이 담겨있음</li>
</ul>
<p>마크업언어 </p>
<p>HTML → 문서 송수신때 사용 ( 블로그, 검색 메인page) : index.html </p>
<pre><code>- &lt;head&gt; &lt;/head&gt; , &lt;body&gt; &lt;/body&gt; , &lt;H1&gt; &lt;/H1&gt;  이런 구조

&lt;book&gt;
&lt;title&gt;Learning XML&lt;/title&gt;
&lt;author&gt;John Doe&lt;/author&gt;
&lt;price&gt;39.95&lt;/price&gt;
&lt;/book&gt;</code></pre><p>XML → extend html 정보 송수신때 사용 </p>
<ul>
<li><code>&lt;title&gt;Learning XML&lt;/title&gt;</code> 이렇게 &lt; &gt;  이런게 많아서 parsing , 해석하는데 오버헤드</li>
</ul>
<p>JSON —&gt; restful 서버 : 백엔드서버 : 정보를 주고받는서버 따라서 문서를 주고받는 서버가 필요 → 그래서 프론트엔드가 필요하다. </p>
<ul>
<li>객체를 표현하는 Object</li>
</ul>
<p><code>&quot;name&quot;: &quot;John Doe&quot;, 
&quot;age&quot;: 30,
&quot;email&quot;: &quot;[johndoe@example.com](mailto:johndoe@example.com)&quot;,</code></p>
<h3 id="5-프론트엔드">5. 프론트엔드</h3>
<ul>
<li>사용자 인터페이스 , view 엔진</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/ae5ddc84-3c46-4f12-8ee3-810882d685be/image.png" /></p>
<h3 id="6-html">6. HTML</h3>
<ul>
<li>HTML 문서 요소</li>
</ul>
<pre><code class="language-java">&lt;p class =“cats”&gt;</code></pre>
<pre><code>class : 속성 - 구조정보 

cats : 속성 값 

&lt;title&gt; = 웹 브라우저의 탭 메뉴 

&lt;body&gt; : 렌더링 할 영역 

&lt;id&gt; : 문서에서 유일한 식별자 설정 , 주로 css, js 요소 찾을때 사용

&lt;class&gt; :  일종의 분류 혹은 종료 </code></pre><pre><code>- 공간분할태그 → &lt;div&gt;   &amp;    &lt;span&gt;</code></pre><pre><code>&lt;div&gt; block 단위 

&lt;span&gt; 웹브라우저의일부영역만 ‘inline’ 형식

- 공간분할태그&lt;iframe&gt;  → HTML문서 내 또 다른 HTML 문서 내장

    하지만  현재는 보안문제로 잘 사용하지않음

    - 겉 페이지와 안 페이지는 독립적으로 렌더링 , life 사이클이 다르다.

- 링크태그 → &lt; a href = “url”&gt;

&lt;a&gt;태그의 target 과 rel속성
</code></pre><p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/39737373-76dd-4e0c-861f-c39d9d88af03/image.png" /></p>