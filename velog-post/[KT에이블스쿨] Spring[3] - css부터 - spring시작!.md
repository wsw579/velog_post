<ul>
<li>오전시간 CSS 실습  —&gt; 실습한 내용 git에 올려둠  —&gt; 깃 링크첨부</li>
</ul>
<hr />
<h3 id="web---http-송수신하는---html문서를-주고받는-서버이다"><strong>Web :  http 송수신하는  , html문서를 주고받는 서버이다.</strong></h3>
<h1 id="1-http란-"><strong>1. http란 ?</strong></h1>
<ul>
<li>http ( hyper text transfer protocol ) : 텍스트 기반 통신규약, 웹 클라이언트와 웹 서버 간에 데이터를 주고 받는데 사용되는 프로토콜</li>
<li>http는 기본적으로 TCP/IP 프로토콜 기반으로 동작 , 기본 포트는 80.</li>
<li>클라이언트는 서버의 IP(목적지)와 포트번호(네트워크에서 어떤 애플리케이션인지 구분하기위해)를 알고있어야 해당정보를 바탕으로 서버와 통신할 수 있다.</li>
<li>(요청,응답) 한 번 이루어지면 연력을 끊는 비연결성특징(HTTP는 비연결형으로 설계되어 인터넷의 분산성과 자원 효율성을 극대화) 갖음</li>
</ul>
<p>→ 서버에서 데이터를 줘야하는데 http는 줄 방법이 없다. </p>
<p>→ 따라서 폴링이라는 방법을 사용 - 폴링:  client가 server한테 가져갈 최신 데이터가 있는지 물어봄</p>
<ul>
<li>서버는 client를 식별할 수 없다 ( 계속 신호가 끊어지니까)  따라서 상태를 기억하기위해 쿠키와 세션이 등장했다.</li>
</ul>
<p>→ 쿠키 : client가 메모장을 가지고 있음 → 메모장에는 관련사이트에 어떤 ip로 접근했을때 로그인정보 , 어떤 사이트에 방문했는지 등 연결되어있지않는데 연결된것처럼 로그인이 되어있고 , 인터넷서핑할때 봤던내용인지 알 수 있음 </p>
<p>→ 세션 : 같은메모장인데 서버가 가지고있을때  </p>
<h1 id="2-http-status-code">2. HTTP Status Code</h1>
<p>2XX :  Success </p>
<p>4XX : client의 오류 , 그렇지만 이건 서버의 판단이므로 100% 맞는건 아니다. </p>
<hr />
<p>TCP(Transmission Control Protocol) : 순서가 중요 , 데이터가 중요(http로 읽어올때 데이터유실되지않음), </p>
<p>UDP : 속도가 중요할때 , 데이터 유실에 덜 민감 → 동영상에 사용</p>
<p>—&gt; UDP header가 크기가 작음 </p>
<ul>
<li>URL
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/5310c08e-33c5-495f-81c5-2c9927545cd1/image.png" /></li>
</ul>
<h1 id="3-웹렌더링">3. 웹렌더링</h1>
<p>Ajax 등장 ! —&gt; 통신을 하면서 다른 처리를 병렬적으로 동시에 처리 </p>
<h3 id="웹-브라우저에서의-렌더링"><strong>웹 브라우저에서의 렌더링</strong></h3>
<ul>
<li><strong>정의</strong>: 웹 브라우저가 HTML, CSS, JavaScript 등의 코드를 읽어 화면에 웹페이지를 그리는 과정.</li>
</ul>
<p>SSR ( Server Side Rendering ) : </p>
<p>서버쪽에서 렌더링준비를 끝마친상태(서버가 html문서만듦)로 클라이언트에 전달하는방식</p>
<p>CSR ( Client Side Rendering ) :</p>
<p>클라이언트인브라우저가렌더링을처리하는방식으로, 서버에서받은데이터를통해클라이언트인브라우저가화면
(View)를 그리는주체가된다 </p>
<p>ex) 치지직 , 아프리카 같이 빨리 화면 전환필요한곳 , 스크롤할때 Ajax(데이터요청) </p>
<h1 id="4-3-tier-architecture-3계층-구조">4. 3-Tier Architecture (3계층 구조)</h1>
<ul>
<li>프리젠테이션 계층 - 클라이언트 : HTML , 자바스크립트 (프로트엔드)</li>
<li>애플리케이션 계층 - 서버  (백엔드 ) →  비즈니스 로직 계층 (도메인서비스 : 회원가입 )</li>
<li>데이터계층 - 데이터베이스</li>
</ul>
<p>데이터베이스 → 데이터베이스관리시스템(DBMS)을사용하여구현</p>
<p>관계형데이터베이스(RDBMS) 는 테이블간의 관계를 중심으로 데이터를 저장하고 관리하는반면,
NoSQL 데이터베이스는 유연한 데이터모델을 제공하여 비정형데이터 나 대규모데이터를다룰때유용</p>
<p>→ Spring은 RDBMS를 다룬다 </p>
<h1 id="5-spring-framework">5. Spring Framework</h1>
<ul>
<li>아무런 기능을 하지않은 뼈대 제공</li>
<li>자바언어기반 프레임워크</li>
</ul>
<p><strong>Framework와 Library의 차이점</strong></p>
<ul>
<li>프레임워크는 제어의 역전 개념이 적용</li>
</ul>
<p>→ 즉, 객체의 생성과 소멸을 프레임워크가 관리</p>
<p>Bean - 객체관리 </p>
<p> <strong>Spring 프레임워크 의존성 주입</strong> </p>
<p>→ @Autowired 어노테이션을통해</p>
<h1 id="6--spring-framework란">6.  Spring Framework란?</h1>
<p>제어의 역행(IoC)과 의존성주입(DI)을 통한 객체간 구성</p>
<p>→  제어의 역행이 적용된 경우 사용자는 new를 이용해 생성된 객체를 사용하지 않고, 스프링에 의해 관리당하는(주입되는) 자바객체를사용한다.</p>
<p>스프링컨테이너(Spring Container) : 스프링에서자바객체들을관리하는공간
빈(Bean) : 스프링 컨테이너가관리하는자바객체</p>
<p>→ 스프링컨테이너에객체, 빈(Bean)을등록하는이유는객체간의의존관계들을스프링이관리하도록하기위해서다.</p>
<ul>
<li>AOP(관점 지향프로그래밍) 지원</li>
</ul>
<p>→ 공통로직을Aspect로모듈화하고핵심적인비즈니스로직에서분리하여재사용하겠다는것이AOP의취지이다.</p>
<ul>
<li><p>POJO는객체지향적인원리에충실하면서, 환경과기술에종속되지않고필요에따라재활용될수있는방식으로설계되
는장점을갖고있다.</p>
<p>OCP : 개방-폐쇄원칙(Open-Closed Principle)</p>
<p>LSP : 리스코프치환원칙(LiskovSubstitution Principle)</p>
</li>
</ul>
<h3 id="애플리케이션-컨텍스트의-주요-기능"><strong>애플리케이션 컨텍스트의 주요 기능</strong></h3>
<table>
<thead>
<tr>
<th><strong>기능</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong>빈 생성 및 관리</strong></td>
<td>애플리케이션에서 필요한 객체를 자동으로 생성하고 관리합니다.</td>
</tr>
<tr>
<td><strong>의존성 주입 (DI)</strong></td>
<td>객체 간의 의존성을 관리하고 필요한 객체를 자동으로 주입합니다.</td>
</tr>
<tr>
<td><strong>빈 생명 주기 관리</strong></td>
<td>빈의 생성, 초기화, 소멸 과정까지 관리합니다.</td>
</tr>
<tr>
<td><strong>이벤트 처리</strong></td>
<td>애플리케이션 이벤트를 관리하고, 이벤트 리스너를 통해 이벤트를 처리합니다.</td>
</tr>
<tr>
<td><strong>국제화</strong></td>
<td>다국어 지원을 위한 메시지 리소스 관리 기능을 제공합니다.</td>
</tr>
</tbody></table>
<h3 id="spring-boot">spring boot</h3>
<ul>
<li>스프링 프레임워크 위에서 실행하는 도구</li>
<li>하나의 애플리케이션 구동하도록 함</li>
<li>내장 서버인 tomket 존재 (http 기반으로 클라이언트의 요청,응답반환역할을 함)</li>
<li>스프링initializer를 이용해 의존성 주입해 프로젝트생성</li>
<li>white label html문서가 뜨는거 자체가 웹서버가 동작한다는 의미</li>
<li>아예 서버가 없으면 개발자도구에서 (F12) 리소스, 헤더가 없다고 나온다</li>
</ul>
<h3 id="정리"><strong>정리</strong></h3>
<table>
<thead>
<tr>
<th><strong>과정</strong></th>
<th><strong>빌드</strong></th>
<th><strong>배포</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong>목적</strong></td>
<td>소스 코드를 실행 가능한 형태로 변환.</td>
<td>빌드된 결과물을 서버나 사용자 환경에 제공.</td>
</tr>
<tr>
<td><strong>출력 결과</strong></td>
<td><code>.jar</code>, <code>.war</code>, 실행 파일 등.</td>
<td>실행 중인 애플리케이션.</td>
</tr>
<tr>
<td><strong>주요 도구</strong></td>
<td>Maven, Gradle 등.</td>
<td>CI/CD 도구(Jenkins, GitHub Actions 등).</td>
</tr>
<tr>
<td><strong>주요 작업</strong></td>
<td>코드 컴파일, 의존성 포함, 패키징.</td>
<td>서버 전송, 실행 환경 구성, 애플리케이션 실행.</td>
</tr>
</tbody></table>