<p>jsp 나온지 오래됨 → 요즘은 <strong>Thymeleaf</strong>나 무스타치 사용함 —&gt; 우린 무스타치 사용 (코드가 더 간결 ) </p>
<p>템플릿 엔진 </p>
<ul>
<li>웹 서버가 클라이언트의 요청을 처리할 때, 특정 데이터를 기반으로 HTML을 동적으로 생성하는 것이 필요할 때 템플릿 엔진을 사용. 이를 통해 웹 애플리케이션은 정적인 HTML 파일이 아닌, 사용자에게 맞춤화된 동적인 페이지를 반환할 수 있다.</li>
</ul>
<p>—&gt; 웹 서버가 <strong>HTML 문서를 동적으로 생성하여 클라이언트에게 전달</strong>하는 방식이라면 템플릿 엔진을 사용하는 것이 일반적이고 필수. 반면에, 웹 서버가 <strong>정보(데이터)만 제공하고 클라이언트에서 HTML을 처리</strong>하는 방식이라면 템플릿 엔진이 꼭 필요하지 않다(SPA) </p>
<p>일반적으로 우리가 사용하는 네이버, 구글 같은 사이트들을 예시로 들자면,</p>
<p>로그인을 할때 아이디,비밀번호를 입력 (웹크라이언트요청) —&gt; 이 데이터를 기반으로 웹서버에서 동적html을 만들어 보낸다 (이때 사용되는 템플릿엔진) </p>
<p>—&gt;  Mustache 사용 </p>
<h2 id="실습">실습</h2>
<ul>
<li>intellij사용</li>
</ul>
<p>프로젝트탐색기에서src&gt; main &gt; java &gt; com &gt;프로젝트디렉토리로이동하면Application.class</p>
<ul>
<li>Spring initializr 에서 추가한  의존성 확인</li>
</ul>
<ol>
<li>Gradle  - 의존성 </li>
<li>Gradle은 오른쪽 <strong>코끼리모양아이콘</strong>을 누르면확인할수있다.</li>
</ol>
<p>→ 아까 추가한  lombok, Spring Web, Spring boot Devtools 확인 가능 </p>
<p>@SpringBootApplication 어노테이션 </p>
<p><code>@SpringBootApplication</code>은 <strong>Spring Boot</strong> 애플리케이션에서 가장 중요한 애너테이션 중 하나입니다. 이 애너테이션은 <strong>Spring Boot 애플리케이션의 시작점을 지정</strong>하고, 여러 다른 기능을 자동으로 활성화하는 역할을 합니다. 사실 <code>@SpringBootApplication</code>은 여러 애너테이션을 조합한 <strong>복합 애너테이션</strong>입니다.
테</p>
<ul>
<li>테스트코드 따로 두기 !  —&gt; 대상에 영향을 주지않도록</li>
</ul>
<p>— &gt;  junit 일반적으로 사용 </p>
<ul>
<li><a href="http://application.properties">application.properties</a> / application.yml  둘 중 하나만 설정하기 !</li>
</ul>
<p><a href="https://mvnrepository.com/">https://mvnrepository.com/</a>  : 중간에 의존성 추가해주기 
<code>compileOnly group: 'org.projectlombok', name: 'lombok'</code></p>
<p>코드 추가하고 → 코끼리 새로고침까지 해야 다운로드 완료 ! ( external 라이브러리에서 확인할 수 있음) </p>
<p>톰캣 = 웹 서버이자 서블릿컨테이너 </p>
<p>실행시 에러 → 근데 서버는 연결됨 white 어쩌고 나온다는게 그 증거 </p>
<p><code>index.html</code><strong>은 웹 애플리케이션의 **첫 번째 진입점 → 추가해주기</strong> </p>
<p><strong>Lombok  -</strong> 자바의 보일러플레이트(반복 코드)를 줄이기 위한 라이브러리로, 애너테이션을 통해 코드 생산성을 향상</p>
<p><strong>Spring Web -</strong> <strong>RESTful</strong> 웹 애플리케이션과 HTTP 기반 서비스를 개발하기 위한 Spring 모듈
<strong>* RESTful 이란 ?</strong> </p>
<ul>
<li><strong>데이터는 서버에서 관리</strong>되고, HTTP를 통해 클라이언트로 전송 <strong>화면은 클라이언트에서 처리</strong>되며, 서버에서 받은 데이터를 렌더링하는 REST (Representational State Transfer) 원칙을 따르는 API 설계 스타일</li>
</ul>
<p><strong>Spring Boot Devtools -</strong>  개발자 생산성을 높이기 위한 도구입니다. 개발 중 애플리케이션을 효율적으로 실행하고 수정 사항을 반영</p>
<p>→ 이런 의존성 도구 없다면 위 기능을 하나도 사용하지 못해 생산성이 떨어진다.   </p>
<ul>
<li>스프링부트는 port 8080에서 기본실행됨 (변경가능)</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/973d492f-4314-4f3d-8726-8a40b6d19052/image.png" /></p>
<ul>
<li>static - index.html 설정</li>
</ul>
<p>static은 정적리소스 (html , css 등 저장됨)</p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/abc44889-4f27-4574-907a-eda162e5db13/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/e315474b-46d3-494a-9253-28c85885298e/image.png" /></p>
<p>→ Spring Boot DevTools 사용시 자동으로 변경됨 </p>
<p><strong>DevTools가 작동하지 않을 때 확인 사항</strong></p>
<ul>
<li><p><strong>IDE 설정 확인하기 !</strong></p>
<p>  IDE에서 프로젝트를 빌드하거나 파일 변경 사항을 자동으로 반영하도록 설정되어 있는지 확인합니다.</p>
<ul>
<li>IntelliJ IDEA: <code>File &gt; Settings &gt; Build, Execution, Deployment &gt; Compiler &gt; Build project automatically</code> 체크</li>
</ul>
</li>
</ul>
<h2 id="postman">Postman</h2>
<p>→  HTTP 요청을 보낼수있는 클라이언트 프로그램으로, 사용자와 서버가 통신하기위한 인터페이스인[API]  개발을마치고 테스트 하기위해 사용한다.</p>
<hr />
<h2 id="spring-mvc">Spring MVC</h2>
<ul>
<li>애플리케이션을 3가지 역할로 구분해서 개발하는 방법론</li>
<li>controller , view , model 로 구분</li>
</ul>
<ol>
<li>controller : 사용자 요청 , 모델과 뷰 사이를 오가면서 조절 </li>
</ol>
<ul>
<li>getMapping(”/hello”) —&gt; <a href="http://localhost:8080">localhost:8080</a></li>
</ul>
<ol>
<li><p>model : 데이터 처리영역 , 로직을 포함한 실제 애플리케이션을구동부분 , db와 연동해 </p>
</li>
<li><p>view : 데이터받아서 html 문서를 만듦 , html 양식과 똑같다</p>
<p> {{ userName ]}    —&gt;  데이터부분 컨트롤러가 넣어줄 내용 </p>
</li>
</ol>
<ul>
<li>DispatcherServlet의 동작 과정</li>
</ul>
<ol>
<li>클라이언트의요청을 DispatcherServlet이받는다.</li>
<li>요청정보를통해이를위임할Controller를HandlerMapping을통해검색한다.</li>
<li>HandlerMapping은 Controller 정보를 DispatcherServlet에게 리턴한다.</li>
</ol>
<p>→ 즉 , DispatcherServlet가 받은 정보에 알맞는 controller 찾음</p>
<h1 id="spring-database-access">Spring DataBase Access</h1>
<ul>
<li>객체중심DB를 사용해서 종속성을 없앤다</li>
<li>mybatis  점점 사용안한다.</li>
</ul>
<p>그럼 종속성있는 DB 란 ? </p>
<ul>
<li>테이블 간 종속성 : 테이블간 외래키로 연결된 관계</li>
<li>컬럼 간 종속성</li>
<li>비즈니스 로직 기반 종속성 : EX) 고객등급변경시 할인정책자동변경됨</li>
</ul>
<p>—&gt;  데이터삭제 시 , 확장성 등 여러문제 발생 </p>
<hr />
<h3 id="orm--object-relational-mapping">ORM : Object Relational Mapping</h3>
<ul>
<li><p>RDB 테이블과 매핑되는 클래스가 Entity 이다.</p>
</li>
<li><p>JPA(Java Persistence API)가 자바 ORM기술</p>
<p>  ⇒ 구현체 hibernate (하이버네이트) </p>
</li>
<li><p>객체(속성,메서드) 개념이 쿼리문에 자동적용</p>
</li>
<li><p>데이터베이스 종속성 줄일 수 있다.</p>
</li>
</ul>
<p>—&gt; 학습곡선 높고  , 모든 쿼리를 대체 할 수 없어 JPQL , QueryDSL 등 기술도 사용 할 수 있어야한다. </p>
<hr />
<h3 id="jpa">JPA</h3>
<ul>
<li>interface 로 만들어졌음 (단순 명세 )</li>
</ul>
<p>—&gt; 구현체인 하이버네이트 필요 </p>
<ul>
<li>영속성</li>
</ul>
<p>@Entity - DB테이블과 대응하는 하나의 클래스 :  영구적으로 저장하는 것 </p>
<ul>
<li>영속성 컨텍스트 : 어플레케이션과 DB사이 객체 보관하는 가상DB역할이다.</li>
<li><strong>Entity 생명주기</strong></li>
</ul>
<p><strong>비영속</strong>  : 자바 heap 메모리에 (홍길동 , a) 저장된 상태</p>
<p><strong>영속</strong> : DB와 heap메모리 데이터가 연결된 상태 (= 실제 통신상태  </p>
<p><strong>준영속</strong> : 영속상태에서 잠깐 끊어진 상태 </p>
<p><strong>예시</strong> </p>
<p>News news = new News(&quot;title&quot; ,&quot;contents&quot;)  : 비영속 </p>
<p>application 프로퍼티가 yml 파일보다 우선순위가 높다.</p>
<p>EntityManager (em) : <strong>엔티티</strong>(객체)와 데이터베이스 간의 상호작용을 담당</p>
<ul>
<li>지연로딩가능</li>
</ul>
<h3 id="jparepository"><strong>JpaRepository</strong></h3>
<p><code>import org.springframework.data.jpa.repository.JpaRepository;</code></p>
<p><code>public interface UserRepository extends JpaRepository&lt;User, Long&gt;</code> </p>
<p><code>{ User = 내가 관리할 객체 , Long = pk가 무슨 자료형인지</code> </p>
<p><code>// 기본적인 CRUD 메서드는 JpaRepository가 제공
// 추가적으로 커스텀 쿼리작성도 가능</code> </p>
<p><code>}</code></p>
<ul>
<li>Spring Data JPA에서 제공하는 JPA의 상위 레벨 인터페이스로, 기본적인 CRUD 작업을 지원하는 <strong>Repository 인터페이스</strong></li>
<li><code>JpaRepository</code>를 상속하면 CRUD 메서드와 페이징, 정렬 기능을 사용할 수 있다.</li>
</ul>
<h3 id="주요-메서드">주요 메서드</h3>
<table>
<thead>
<tr>
<th>메서드</th>
<th>설명</th>
</tr>
</thead>
<tbody><tr>
<td><code>save(S entity)</code></td>
<td>엔티티를 저장하거나 업데이트</td>
</tr>
<tr>
<td><code>findById(ID id)</code></td>
<td>ID로 엔티티 조회</td>
</tr>
<tr>
<td><code>findAll()</code></td>
<td>모든 엔티티 조회</td>
</tr>
<tr>
<td><code>deleteById(ID id)</code></td>
<td>ID로 엔티티 삭제</td>
</tr>
<tr>
<td><code>findAll(Sort sort)</code></td>
<td>정렬된 목록 조회</td>
</tr>
<tr>
<td><code>findAll(Pageable pageable)</code></td>
<td>페이징된 목록 조회</td>
</tr>
</tbody></table>
<hr />
<h3 id="실습--04-jpa">실습 : 04. jpa</h3>
<p><code>ddl-auto: create</code> : </p>
<p>프로그램 실행시 마다 새로만듦 (데이터유지X) 
<code>ddl-auto: update</code> : 
애플리케이션의 엔티티 클래스와 데이터베이스 테이블을 비교하여 <strong>자동으로 스키마를 업데이트 (증분)</strong> </p>
<p>—&gt; 만약 업데이트됐는데 삭제시 직접쿼리문 작성해야함 </p>
<p><code>ddl-auto: validate</code> :  매핑되는 테이블 존재 유뮤 확인만 </p>
<p>→ 안정적DB , 없다고 평가되면 실행되지않음 </p>
<ul>
<li><strong>도메인객체 : @Entity</strong></li>
</ul>
<p><code>@Entity</code> 선언할 때 사용하는 </p>
<p><code>@Id</code>는 JPA(Java Persistence API)에서 해당 클래스의 기본 키(primary key)를 지정하는 데 사용.</p>
<p><strong>기본 키</strong>는 데이터베이스에서 각 엔티티(행)를 고유하게 식별하는 데 필요한 필수적인 요소이다. </p>
<p>—&gt; 즉 , <code>@Entity</code>가 선언된 클래스에는 반드시 <strong><code>@Id</code> 필드있어야 매핑가능하다.</strong> </p>
<hr />
<h2 id="bootstrap">Bootstrap</h2>
<div class="container">  - 전체 콘텐츠 감싸는 요소 
<div class="row">
<div class="col-md-4">열 1</div>
<div class="col-md-4">열 2</div>
<div class="col-md-4">열 3</div>
</div>
</div>

<ol>
<li>설정파일 :  Spring Boot에서 한글 깨짐을 방지</li>
</ol>
<p>server:
servlet:
encoding:
force-response: true</p>
<ol>
<li>디렉터리 구조 </li>
</ol>
<ul>
<li>이 부분을 잘 설정해주지 않아서 계속 <a href="http://localhost">localhost</a> 창이 뜨지 않았다 ! 주의 !</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/3d4bb4b3-f742-4af9-9827-dcc855548b8d/image.png" /></p>
<ul>
<li>구조를 잘보고 설정하기</li>
<li>경로를 잘 보지 않으면</li>
</ul>
<p>src &gt; main &gt; resources &gt; templates &gt; layouts
src &gt; main &gt; resources &gt; templates &gt; news</p>
<p>—&gt; 템플릿 경로 명확히 지정하기</p>
<p>—&gt; 그냥 추가했더니 이렇게 설정됨 src &gt; main &gt; resources &gt; templates &gt; layouts &gt; news </p>
<p>—&gt; templates &gt; layouts의 news 파일로 인식해버려서 그렇다. </p>
<ul>
<li>mustache 재사용</li>
</ul>
<!-- 부분 템플릿 호출 -->
<p>{{&gt; footer}}</p>
<p>이렇게 부분 템플릿 호출해서 재사용가능 </p>
<ul>
<li>레이아웃 템플릿을 삽입할 때에는 원하는 위치에서 {{&gt;파일 경로/파일명}} 형식으로 작성</li>
</ul>
<p>—&gt; {{&gt;layouts/footer}}</p>
<p>@Controller - @GetMapping(&quot;/hello&quot;)  —&gt;  “<a href="http://localhost:8080">localhost:8080</a>/hello” url에 요청 </p>
<h2 id="사용-비교"><strong>사용 비교</strong></h2>
<table>
<thead>
<tr>
<th><strong>어노테이션</strong></th>
<th><strong>주로 사용하는 경우</strong></th>
<th><strong>데이터 전달 방식</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong><code>@GetMapping</code></strong></td>
<td>조회 작업 (예: 검색, 데이터 읽기)</td>
<td>URL 쿼리 파라미터, 경로 변수</td>
</tr>
<tr>
<td><strong><code>@PostMapping</code></strong></td>
<td>생성 작업 (예: 폼 제출, 데이터 저장)</td>
<td>HTTP 요청 본문 (<strong><code>@RequestBody</code></strong>)</td>
</tr>
</tbody></table>
<p><a href="https://mvnrepository.com/">https://mvnrepository.com/</a></p>
<p>—&gt; 추후 의존성 추가 할 수 있도록  하는 사이트</p>