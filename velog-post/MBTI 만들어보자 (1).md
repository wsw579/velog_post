<p><em>*<em>2025.06.26 *</em></em></p>
<p>원래는 게시글 작성/수정/삭제 이후 여러자잘한 기능과 로그인/회원가입을 진행할 줄 알았는데 MBTI 진행 ... ! 
<a href="https://www.16personalities.com/ko/">https://www.16personalities.com/ko/</a></p>
<h4 id="mission-1">MISSION 1</h4>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/8296a7ca-f7fd-4825-8cd4-a4307971b0b5/image.png" /></p>
<ol>
<li>먼저 유형이 왜 저렇게 되는지 의문이 들어서 찾아봤더니 딱 ENFP 이렇게 나오는게 아니라 %로 나오다보니 상반된 유형으로 구분되는거라고 한다. (아닐수도)</li>
<li>일단 BOARD 테이블의 BOARD_TYPE 사용해서 유형 생성 및 구분을 한다. 위에서도 말했다 싶이 유형들의 세부적인 % 도 줘야해서 POINT_TYPE 컬럼을 하나 추가했다. 그리고 BOARD_COMMENT에는 질문지를 작성하도록 하고</li>
<li>일단 DB에 데이터를 넣어줬다. </li>
</ol>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/48df5ef0-7a04-4565-8222-427923dfa8f9/image.png" /></p>
<h4 id="mission-2">MISSION 2</h4>
<ol start="4">
<li>그 다음 radio를 사용해서 동의/비동의 선택 만들어주기 
실제 mbti 사이트 들어가면 개발자 브라우저에 나와있어서 참고하면 될 것 같다. 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/cb7e2835-b6c2-4efd-b236-9680ab174a32/image.png" /></li>
</ol>
<blockquote>
<p>MyBatis XML 구문  </p>
</blockquote>
<pre><code>&lt;select 
    id=&quot;boardView&quot;                              
&lt;!-- ① 이 SQL 구문을 호출할 때 사용할 Mapper의 메서드 이름 --&gt;
    parameterType=&quot;com.spring.board.vo.BoardVo&quot; 
&lt;!-- ② 이 쿼리에 전달되는 파라미터 객체 타입이야.
즉, 이 SQL은 BoardVo라는 객체가 파라미터로 넘어와야 작동함--&gt;
    resultMap=&quot;boardVo&quot;&gt;                        
&lt;!-- ③ 쿼리 결과를 Java 객체(BoardVO)에 어떻게 매핑할지 규칙을 정한 것</code></pre><p>보통 아래처럼 정의돼 있음</p>
<pre><code>&lt;resultMap id=&quot;boardVo&quot; type=&quot;com.spring.board.vo.BoardVo&quot;&gt;
    &lt;id property=&quot;boardNum&quot; column=&quot;BOARD_NUM&quot;/&gt;
    &lt;result property=&quot;boardType&quot; column=&quot;BOARD_TYPE&quot;/&gt;
    &lt;result property=&quot;boardComment&quot; column=&quot;BOARD_COMMENT&quot;/&gt;
    &lt;result property=&quot;pointType&quot; column=&quot;POINT_TYPE&quot;/&gt;
&lt;/resultMap&gt;</code></pre><h3 id="🚨warn-html에서-bootstrap과-css를-잘-적용했음에도-라디오-버튼이-동그랗게-커스텀되지-않는다">🚨WARN: HTML에서 Bootstrap과 CSS를 잘 적용했음에도 라디오 버튼이 동그랗게 커스텀되지 않는다</h3>
<blockquote>
<p><strong>해결과정</strong> <br /> 기존에 있던  HTML설정과 충돌 --&gt; 기존 설정을 지워주니 잘 나온다.</p>
</blockquote>
<h3 id="🚨-404-오류">🚨 404 오류</h3>
<p>  <img alt="" src="https://velog.velcdn.com/images/victoryone/post/28c1b7ad-2623-49e4-beb0-4134667b6c23/image.png" /></p>
<blockquote>
<p>  <strong>해결과정</strong> <br />잘 쓰던 url에서 갑자기 404오류 <br />404오류는 클라이언트에서 url로 요청을 했는데 서버가 관련 데이터를 찾이못해 응답하지 못한 오류이다. <br />근데 Controller에서 url을 바꾼것도 아니고 , url주소를 잘못쓴것도 아니고 , 방화벽을 건드린것도 아닌데 뭘 까 ? 하다가 동기가 껐다키라고해서 맞네.. 하고 껐다 키니까 된다 (역시 만병통치 재부팅) </p>
</blockquote>