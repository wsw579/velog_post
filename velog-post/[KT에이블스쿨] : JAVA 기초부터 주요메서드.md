<blockquote>
<p>** JAVA수업 시작 ! 
강사님이 되게 잘설명해주셔서 아는내용도 몰랐던내용도 재밌게 들었다.**</p>
</blockquote>
<ul>
<li><strong>고급언어</strong>: 사람과 기계어 사이를 매개하는 프로그래밍 언어(예: 자바, C, C++)</li>
<li><em>컴파일*</em>: 프로그래밍 파일을 기계어 파일로 번역 (.java → .class)
고급언어로 작성된 소스코드는 컴파일러를 이용해 <strong>기계어</strong>로 변환된다.</li>
<li><strong>컴파일언어</strong> : 자바 , C , C++ , C#</li>
<li><em>인터프리터(스크립트) 언어*</em> : 파이썬 , 자바스크립트 , PHP 등</li>
</ul>
<p><strong>JAVA 주요특징</strong></p>
<ol>
<li><strong>객체지향</strong> : 모든 것을 객체로 취급 , 클래스를 통해 객체 정의</li>
<li><strong>플랫폼 독립성</strong> : 자바가상머신(JVM) 위에서 실행되면서 , 한 번 작성한 코드는 어떤 플랫폼에서도 실행할 수 있다. </li>
</ol>
<ul>
<li><strong><em>자바의 플랫폼 독립성은 JVM 덕분</em></strong><ol>
<li><strong><em>개발자는 자바 코드를 작성하고 바이트코드(.class)로 컴파일합니다.</em></strong></li>
<li><strong><em>각 운영체제에 맞는 JVM이 이 바이트코드를 변환하고 실행합니다.</em></strong></li>
<li><strong><em>따라서 자바 프로그램은 운영체제나 하드웨어와 무관하게 동일하게 실행됩니다.</em></strong></li>
</ol>
</li>
</ul>
<ol start="3">
<li><strong>자동 메모리 관리</strong> </li>
</ol>
<p><strong>자바 개발 환경 구성</strong></p>
<ul>
<li><p><strong>JVM</strong>(소스코드로부터 만들어지는 자바 바이트 코드를 실행)</p>
</li>
<li><p><strong>JRE</strong> ( 컴파일된 JVM실행되기 위한환경 , JVM과 JavaAPI 함께제공 )</p>
</li>
<li><p><strong>JDK</strong>(개발을위한 , JRE와 컴파일러 등 포함)</p>
</li>
<li><p>컴파일러(javac)</p>
</li>
</ul>
<p><strong>Intellij IDEA 대략적인 특징</strong></p>
<ul>
<li>Utimate(유료, 30일무료) : 자바말고도 다른언어 가능</li>
<li>Community : 자바만</li>
</ul>
<p><strong>자바클래스 프로젝트 내 모듈생성</strong>
프로젝트 &gt; 모듈 &gt; 패키지 &gt; 클래스 순서로 계층 구조</p>
<ol>
<li><strong>프로젝트</strong>
전체 프로그램을 개발하는 최상위 단위
예를 들어, &quot;쇼핑몰 웹사이트&quot;를 개발한다고 하면 이게 하나의 프로젝트이다.
프로젝트는 여러 모듈로 나뉘어질 수 있다.<br /></li>
<li><strong>모듈</strong>
프로젝트를 구성하는 논리적 단위.
각 모듈은 서로 다른 역할을 맡을 수 있으며, 모듈 간 의존성을 설정해 협력한다.
예를 들어, 쇼핑몰 프로젝트에서 다음과 같은 모듈이 있을 수 있다.
user.management 모듈: 사용자 관련 기능 (회원가입, 로그인 등)
product.catalog 모듈: 상품 카탈로그 관리
order.processing 모듈: 주문 처리 관련 기능<br /></li>
<li><strong>패키지</strong>
모듈 내에서 파일(클래스)을 관리하기 위한 하위 구조.
관련된 클래스들을 묶는 단위로, 클래스가 많아질 때 체계적으로 관리하기 위해 사용한다. 
예를 들어, 
 user.management 모듈 내부의 패키지는 다음과 같이 구성:<br /> com.example.user → 사용자 기본 정보 관리 클래스들
 com.example.user.auth → 인증 관련 클래스들 (로그인, 비밀번호 변경)<br /></li>
<li><strong>클래스</strong>
가장 작은 코드 단위로, 프로그램의 동작을 정의.
클래스는 패키지에 포함되고, 객체지향적으로 데이터를 처리하거나 기능을 수행합니다.<br />예를 들어, com.example.user.auth 패키지에는 다음과 같은 클래스가 있을 수 있습니다:
 LoginService: 로그인 처리 클래스
 PasswordResetService: 비밀번호 초기화 처리 클래스</li>
</ol>
<blockquote>
</blockquote>
<p>프로젝트: ShoppingMall
│
├── 모듈: user.management
│ ├── 패키지: com.example.user
│ │ ├── 클래스: User
│ │ ├── 클래스: UserService
│ │
│ ├── 패키지: com.example.user.auth
│ ├── 클래스: LoginService
│ ├── 클래스: PasswordResetService
│
├── 모듈: product.catalog
│ ├── 패키지: com.example.product
│ │ ├── 클래스: Product
│ │ ├── 클래스: ProductService
│
├── 모듈: order.processing
├── 패키지: com.example.order
├── 클래스: Order
├── 클래스: OrderService</p>
<p><strong>정리</strong>
프로젝트: 전체 프로그램
모듈: 프로젝트를 논리적으로 나눈 단위 
패키지: 모듈 내에서 클래스들을 묶는 논리적 단위
클래스: 실제 프로그램의 동작을 정의하는 단위</p>
<p><strong>추가적인내용</strong></p>
<p>모든 클래스는 패키지내 고유하다
→ 패키지를 폴더라고 생각하면 다른 패키지이면 클래스이름이 동일해도 상관없다.
→ 패키지 이름은 1. 소문자만 사용권장 2. .으로 연계한다.
→ ex) com.example.hello
: com이란 폴더 내 example 폴더 내 hello 폴더를 만든다는 말</p>
<ul>
<li>자바클래스 이름은  <strong>첫글자는 대문자 : 카멜표기법</strong></li>
<li>자바타입의 종류 : 데이터가 저장되는 메모리와 프로그램에서의 처리방식 명시</li>
<li>기본형타입 &amp; 참조형 타입</li>
<li>기본형타입은 Stack메모리에 저장</li>
<li>자바 기본형타입 총 8종류 byte , short , int , long , float , double , char , boolean</li>
</ul>
<p><strong>스택 vs 힙</strong></p>
<ul>
<li>스택메모리는 메서드 내 지역변수 저장소 , 메서드 호출과 함께 할당되고 메서드 끝나면 해제 , 속도가 빠르고 관리 단순</li>
<li>힙 메모리는 객체와 인스턴스가 저장되는 영역 , 가비지 컬렌션 대상 , <strong>런타임 중 객체가 동적으로 생성 및 관리</strong>되는 메모리 영역 , 스택에 비해 메모리관리 복잡</li>
</ul>
<p><strong>자바 변수</strong>
int a =5 , b =3 ; (0)</p>
<p>int a = 2 ; (0) 여기서 a를 변수 ,
a = 2; (x) 여기에는 메모리 할당(데이터타입선언)을 안해주어서 변수선언이 안됨</p>
<p>컴파일언어는 컴파일러하기전 얼마나 할당할지 미리 알아야한다.</p>
<p><strong>비교연산자</strong></p>
<p>'A' &gt;'B' : 문자표상의 숫자이기때문에 비교할 수 있다. 답은 아니다
65 &gt; 66 결과 False</p>
<h3 id="q-과--그리고-와--사이에-차이가-있나요">Q. &amp;과 &amp;&amp;, 그리고 |와 || 사이에 차이가 있나요?</h3>
<p>(3 &lt;2) &amp;&amp; (4&gt;1) : 이때 앞에가 false이면 뒤에건 무조건 실행도 안한다.
(3 &lt;2) &amp;  (4&gt;1) : 이때 앞에가 false여도 뒤에건 무조건 실행한다.</p>
<p>하지만 &amp;&amp;일때 뒤에가 프로그램 내 필요한 조건일 수 있기 때문에 실행을 안해서 논리오류가 생길 수 있다.</p>
<h3 id="q-문자열-비교에-대해서-equals랑--차이점">Q. 문자열 비교에 대해서 equals랑 == 차이점</h3>
<p>== </p>
<p>용도: 두 객체가 같은 메모리 주소를 참조하는지 확인합니다.
문자열의 실제 내용이 같은지는 확인하지 않습니다.</p>
<p>equals
용도: 객체의 <strong>내용(content)</strong>을 비교합니다.
결과: 두 문자열의 <strong>값(문자열 내용)</strong>이 같은지를 확인합니다.</p>
<ul>
<li>기본형타입과 달리 참조형타입은 빈 객체를 의미하는 Null 존재</li>
<li>참조형타입은 주소저장변수이다.</li>
</ul>
<h3 id="string"><strong>String</strong></h3>
<p>String은 클래스이다 . 문자열은 문자열의 집합 </p>
<p>예외적으로 new를 없이 사용해도된다.
하지만
String s1 = new String(&quot;hello&quot;) ;
String s2 = &quot;hello&quot; ;
두 s1,s2는 다른객체이다. 두 String이 들어간 주소가 다르기때문이다.
String은 주소값을 저장하는 레퍼런스(참조형)변수이기 때문에 s1,s2에는 주소값이 저장되어있다.
s1,s2 대입된 hello를 비교하는게 아니라 hello가 저장된 주소값을 비교하는 것이다.</p>
<blockquote>
<p>자바에서는 불변(immutable) 객체로 즉, 한 번 생성된 문자열은 변경할 수 없다.
그래서 StringBuilder로 생성하고 sb.toString()으로 변경해준다.</p>
</blockquote>
<p><strong>문자열 비교</strong></p>
<ol>
<li>== , != : 주소값 비교</li>
</ol>
<ul>
<li>compareTo(String s) 문자열을 사전순으로 비교해 정수 값 반환</li>
<li>compareToIgnoreCase(String s) 대소문자 무시 문자열을 사전순으로 비교해 정수 값 반환</li>
<li>equals(String s) 문자열 s와 현재문자열 비교 후 true , false 반환</li>
<li>equalsIgnoreCase(String s) 대소문자 무시 문자열 s와 현재문자열 비교 후 true , false 반환</li>
</ul>
<p>** String 주요 인스턴스 메서드**</p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/efd427e8-0c3a-46b2-9b18-c0fe187f7a77/image.png" /></p>
<ul>
<li>compareTo는 앞에서부터 비교한다. 문자열이 끝날때까지 다른점이 없으면 0
h - h 같고 e - e 같고 이런식으로 비교한다.</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/2b84a092-1d6f-49b1-bc33-34a982397c67/image.png" />
<strong>결과 str1과 str3비교결과 : -32</strong></p>
<ul>
<li><p><code>'H'</code>의 유니코드 값: <strong>72</strong></p>
</li>
<li><p><code>'h'</code>의 유니코드 값: <strong>104</strong></p>
</li>
<li><p>차이: <code>72 - 104 = -32</code></p>
</li>
<li><p>char 형식 String으로 출력하기</p>
</li>
</ul>
<p>int[] intArray = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};</p>
<p>System.out.println(intArray); 틀림 </p>
<p>System.out.println(Arrays.toString(intArray)); </p>
<ul>
<li><strong>String의 subString()</strong></li>
</ul>
<p><code>String</code> 객체는 불변(immutable) 이기 때문에, <code>str.substring(5)</code>와 같은 메서드를 호출하면 <strong>원래의 문자열 <code>str</code>이 변경되지 않는다.</strong></p>
<p>→  <strong>새로운 문자열 객체</strong>가 생성되고 원본 String str은 변하지 않는다. </p>
<hr />
<ul>
<li><strong>String의 reverse()</strong></li>
</ul>
<p>자바의 기본 <strong><code>String</code> 클래스</strong>는 문자열이 불변(immutable)하기 때문에, 문자열을 뒤집으려면 <strong><code>StringBuilder</code></strong> 또는 <strong><code>StringBuffer</code></strong>와 같은 <strong>가변(mutable)</strong> 문자열 클래스를 사용해야 합니다.</p>
<h3 id="✅-string은-불변immutable"><strong>✅ <code>String</code>은 불변(Immutable)</strong></h3>
<ul>
<li><p>자바의 <strong><code>String</code> 클래스</strong>는 불변이기 때문에 문자열의 내용을 변경할 수 없다.</p>
</li>
<li><p>예를 들어, 문자열에 문자를 추가하거나 내용을 변경하려고 하면, 항상 <strong>새로운 객체</strong>가 생성된다.</p>
</li>
<li><p><strong>String 클래스에서 제공하는 정적메서드</strong></p>
</li>
</ul>
<p>앞에서 사용한 String a = “hello” ; 일때  a.trim() 은 a인스턴스 생성하고 사용되는데</p>
<p>정적메서드 그냥 . 찍고 사용한다.</p>
<p><strong>정적메서드 종류</strong></p>
<ul>
<li><p>join : + 역할</p>
<ul>
<li><p>String.join(” ” , String a, String b ,String c)</p>
<blockquote>
<p>“ “ 공백기준으로 합친다.</p>
</blockquote>
</li>
</ul>
</li>
<li><p>valueOf : 문자열로 변환</p>
<ul>
<li><p>String.valueOf</p>
<blockquote>
<p>int number = 42;
String numberString = String.valueOf(number);</p>
</blockquote>
</li>
</ul>
</li>
<li><p>format : 문자열을 원하는 형식으로 포맷팅</p>
</li>
</ul>