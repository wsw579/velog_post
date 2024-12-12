<h3 id="배열">배열</h3>
<ul>
<li><p>배열 선언
→  *<em>int [] score ;  int score [] ;  *</em>     int score [5]; (X)</p>
</li>
<li><p>배열 선언과 생성
→ score = int new [5];  </p>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/bf8439c7-8e7c-433f-8ac5-816f482f665f/image.png" />
→ 각 scores[i] 는 4byte 크기</p>
<p><code>int [] scoreM1 = {100,90,50,95,85};  // 배열 선언 3가지 방법</code> </p>
<p><code>int [] scoreM2 = new int []{100,90,50,95,85};</code></p>
<p><code>int [] scoreM3 coreM3 = new int [] {100,90,50,95,85};</code></p>
<p>번외로 </p>
<p><code>int [] a = new int [5] ;  a[0] = 1, a[1] =2 …</code> </p>
<h3 id="q-파이썬-enumerate처럼-for문-돌때-요소와-인덱스-같이-가져오는-방법이-있나요-for-index-int-score--scoremethod2-처럼">Q. 파이썬 enumerate()처럼 for문 돌때 요소와 인덱스 같이 가져오는 방법이 있나요? for( index, int score : scoreMethod2) 처럼</h3>
<p><code>: 없다. → Stream 사용하기</code> </p>
<ul>
<li><h3 id="stream"><strong>Stream</strong></h3>
</li>
</ul>
<ul>
<li><h3 id="java-collection-framework-구조"><strong>Java Collection Framework 구조</strong></h3>
</li>
</ul>
<h3 id="q-length와-length함수차이">Q. length와 length()함수차이</h3>
<p><strong>length() ** 
: **String 클래스에서 제공하는 함수 length()</strong></p>
<p><strong>length</strong>
: <strong>Array에서 length 변수형태 수</strong></p>
<h3 id="for문">for문</h3>
<p>for(itn i = 0 ; i &lt; 10; i++ ) 이때 <code>; 은 구문을 구분해준다.</code> </p>
<p>for(단일객체선언: 배열) 이때 for문은 <code>for(int score : scores)</code> 이렇게 쓴다.</p>
<p><strong>배열은 모두 힙메모리로 저장된다 
배열을 초기화시키지않아도 0으로 초기화된다. 
스택메모리에 저장되는것은 초기화되지않기때문이다.</strong></p>
<h3 id="다차원배열">다차원배열</h3>
<pre><code class="language-jsx">1)  다차원배열 원소 출력 for-each문
for (int[] score : scores) { 
  // scores의 각 행(즉, 1차원 배열)을 순회    
    for (int i : score) {   
        System.*out*.println(i + &quot; &quot;);
        }
        System.*out*.println();   
 }    </code></pre>
<pre><code class="language-jsx">2) 다차원배열 원소 출력 for문
for(int i=0; i&lt;scores.length; i++){
    for(int j=0; j&lt;scores[i].length; j++){
          System.*out*.println(scores[i][j]+ &quot; &quot;);
          }
          System.*out*.println();   
 }   </code></pre>
<p><strong>Arrays 배열을 컨트롤하는 클래스 
scores[0] = 주소값이 나옴 
배열로 출력하고 싶으면 이렇게 구현</strong>
<code>System.out.println(Arrays.deepToString(scores));</code></p>
<p><code>int []temp = scores[0]  // 얇은 복사 , 메모리주소를 같이 참조하게됨</code></p>
<p>*<em>배열은 고정된 크기가있어서 , 원소를 추가,제거하는데 어려움이 있다. 
정적배열에서는 인데스를 id처럼 사용할 수있다. 
그래서 동적배열을 사용한다. *</em></p>
<h3 id="동적배열--arraylist클래스">동적배열 : ArrayList&lt;클래스&gt;</h3>
<pre><code> ArrayList &lt;Integer&gt; a

 = new &lt;Integer&gt; ArrayList &lt;&gt;();  

 = new ArrayList &lt;&gt;(); 

→ ArrayList&lt;Long&gt;

→ ArrayList&lt;Float&gt;

→ ArrayList&lt;Double&gt;

→ ArrayList&lt;Charater&gt;

→ ArrayList&lt;Boolean&gt;
</code></pre><h3 id="arraylist-원소접근">ArrayList 원소접근</h3>
<p>a.add(데이터)<br /><strong>//  마지막에 원소추가</strong></p>
<p><code>cf</code>
a.add(1, 데이터)<br />//  <strong>1인덱스에 원소추가</strong> </p>
<p>list1.addAll(list2); 
<strong>// list2의 모든 요소를 list1에 추가</strong></p>
<p>a.remove(인덱스)<br /><strong>// 인데스번호 원소 제거 → 자동으로 다시 재정렬</strong></p>
<p><strong>그래서 동적배열에서 인덱스는 가변적이다.</strong></p>
<p><code>cf</code>
<code>stringList.remove(&quot;Python&quot;);</code><br /><strong>// 이렇게 원소 자체를 지울 수도 있다.</strong> </p>
<p><code>stringList.remove(0);</code>
→ <code>stringList.remove(Integer.valueOf(0)); // 리스트에서 값이 0인 요소를 삭제</code></p>
<p>a.get(인덱스)<br /><strong>//  인덱스 번호 원소 가져오기</strong> </p>
<p>a.size()<br /><strong>//  동적배열 크기</strong> </p>
<h3 id="arraylist-2차원배열-만들기">ArrayList 2차원배열 만들기</h3>
<pre><code class="language-jsx">import java.util.ArrayList;

public class TwoDArrayListExample {
    public static void main(String[] args) {
        // 2차원 ArrayList 선언
        ArrayList&lt;ArrayList&lt;Integer&gt;&gt; twoDimensionalList = new ArrayList&lt;&gt;();

        // 행 추가
        ArrayList&lt;Integer&gt; row1 = new ArrayList&lt;&gt;();
        row1.add(1);
        row1.add(2);
        row1.add(3);
        twoDimensionalList.add(row1); // 첫 번째 행 추가

        ArrayList&lt;Integer&gt; row2 = new ArrayList&lt;&gt;();
        row2.add(4);
        row2.add(5);
        row2.add(6);
        twoDimensionalList.add(row2); // 두 번째 행 추가

        // 출력
        for (ArrayList&lt;Integer&gt; row : twoDimensionalList) {
            System.out.println(row);
        }

        // 특정 요소 접근 (1행 2열)
        System.out.println(&quot;Element at [0][1]: &quot; + twoDimensionalList.get(0).get(1)); // 출력: 2
    }
}
</code></pre>
<ul>
<li><strong>ArrayList  검색 , 추가 할때 자주사용 → 컬렉션마다 자주 사용하는 용도 파악!</strong></li>
</ul>
<p><strong>객체배열</strong> </p>
<pre><code class="language-java">class Ball {
    String name; // 디폴트 (같은패키지, 같은클래스)
    public void setName(String name) {this.name = name;}
    public String getName() {  return name;}
}

public class BallArray {
    public static void main(String[] args) {
        Ball[] balls = new Ball[5];
        // 객체배열
        for(int i = 0; i &lt; 2; i++){
            balls[i] = new Ball();
            balls[i].setName((i+1)+ &quot; 번 Ball &quot;);
        }

        for(Ball ball : balls){
            if(ball != null){
                System.out.println(ball.getName());
            }
            else {
                System.out.println(&quot;null&quot;);
            }
        }
    }
</code></pre>
<p><strong>열거타입  : 서로 연관된 사건들을 모아 상수로 정의한 java.lang.Enum 클래스의 자식 클래스</strong> </p>
<p><strong>enum = class와 비슷한 역할</strong></p>
<p><strong>enum Gender  : 열거타입이름 {  MALE , FEMALE  : 상수목록 }</strong></p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/8b580fe5-bcc5-4149-8fd6-2b76f8371dc4/image.png" /></p>
<h3 id="제어문">제어문</h3>
<p><strong>if</strong></p>
<p><code>char</code>는 16비트의 유니코드 값으로 저장되므로, 문자 '9'는 <code>57</code>이라는 정수로 표현됩니다.</p>
<p>유니코드에서 
'A'는 <strong>65</strong>, 'Z'는 <strong>90</strong>, 'a'는 <strong>97</strong>, 'z'는 <strong>122</strong>로 대응 </p>
<p><strong>while (조건참일시 실행){</strong></p>
<p>break; // 안써주면 무한루프</p>
<p>}</p>
<p><strong>do - while : 일단 한번은 무조건 실행</strong> </p>
<p>do{</p>
<p><strong>무조건 한번은 실행됨</strong></p>
<p>}while(조건문);</p>
<h2 id="객체지향">객체지향</h2>
<ul>
<li>소프트웨어 객체는 현실세계의 객체를 필드(값 = 데이터) 와 메서드 (기능 = 행동)으로 모델링한 것 → 이것을 class라고한다.</li>
</ul>
<p>ex )  321학번(필드) 가진 학생이 수강신청을 하는 행위 (= 메서드)</p>
<ul>
<li>소프트웨어 객체는 상태를 필드로 정의하고 , 동작을 메서드로 정의</li>
</ul>
<p><strong>현실세계</strong>   상태: 꺼짐 , 켜짐 동작 : 켜다 , 끄다  = class </p>
<p>그럼 인스턴스는 ? </p>
<p><strong>인스턴스화 되면 상태를 갖는다 = new 가 이렇게 만들어줌</strong></p>
<p>눈에 보이는 상태가 되어야(= 동작이 가능하게 만들어줌 ) <strong>힙 메모리에 저장된다.</strong> </p>
<ul>
<li>객체지향 프로그래밍 특징</li>
</ul>
<p><strong>→ 캡슐화 :</strong> <strong>외부에서는 특정 내부 정보를 알 수 없도록 하는 데이터은닉</strong> </p>
<p>ex) ‘홍길동’이름을 그대로 반환하지 않고 홍*동 처럼 반환하는 예시 </p>
<p><strong>→ 상속 : 어떤 객체를 만들었을때 기능의 확장 &amp; 구체화를 위해 사용한다.</strong> </p>
<p>ex) animal(추상적) - 호랑이 ( 꼬리리의 길이 = 상태를 확장 , 어흥!하고싶다 = 기능을 확장한다.) </p>
<p><strong>→ 다형성 : 동일한 명령을 내리더라도 객체 종류에 따라 다르게 실행된다.</strong></p>
<p><strong>ex)  굉장히 좋은 예시</strong> </p>
<p> 주인공의 기능 中 <strong>공격한다() 메서드</strong> 가 있을때 </p>
<p>공격한다() { this.무기 = 휘두른다() }  <strong>// 똑같은 행동을 하는데 , 내가 들고있는 무기종류에따라 행동이 달라진다.</strong> </p>
<p>무기 class { 휘두른다() } - 여러 무기 객체가 생길 수 있다.</p>
<p>→ ** 그럼 주인공은 변경하지 않아도 된다. 
그래도 무기객체가 다양하게 변화할 수 있다.**</p>