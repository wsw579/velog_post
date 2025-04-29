<h2 id="docker를-왜-공부하냐-">Docker를 왜 공부하냐 ?</h2>
<p>개발자분들 유튜브를 자주 보는 편인데 Docker에 대해 다룬 영상을 보았다. 요새 정말 많은 회사에서 Docker를 사용중이고 그 이유는 너무나도 편하다는 장점이 있다는 것이다. </p>
<blockquote>
<p>이유는 바로 &quot;이식성&quot; : 특정 프로그램을 쉽게 다른 곳에 설치 및 실행하는 특성 
즉, 여러가지 이유로(버전, OS문제 , 보안 등) 프로그램이 설치되지 않을 때 , 개발할 때 에러가 나는 문제를 해결할 수 있다는 것이다.  </p>
</blockquote>
<p>매번 똑같은 설정, 옵션 , 운영체제 등 항상 일관되게 프로그램 설치 가능하다는 뜻 이다.</p>
<hr />
<h2 id="ip-와-port">IP 와 Port</h2>
<p>통신을 위해서는 IP와 Port가 필요 </p>
<p>IP = 컴퓨터 주소 = 192.168.1.1 / 도메인주소 <a href="https://www.naver.com">https://www.naver.com</a> 
Port = 컴퓨터 내 실행되고 있는 특정 프로그램 주소 </p>
<p>브라우저는 Port 80으로 기본적으로 통신 , 도메인주소만 있어도 통신 가능 </p>
<table>
<thead>
<tr>
<th>Well-Known-Port 포트 번호</th>
<th>용도 (서비스)</th>
</tr>
</thead>
<tbody><tr>
<td>22</td>
<td>원격 접속을 위한 SSH</td>
</tr>
<tr>
<td>80</td>
<td>HTTP</td>
</tr>
<tr>
<td>443</td>
<td>HTTPS</td>
</tr>
</tbody></table>
<p>위 사항은 규약일뿐 무조건 지켜야하는건 아니다. Spring Boot 개발할 때 HTTP 8080으로 접속하는 경우가 있다.    </p>
<hr />
<h2 id="docker-🐋-">Docker 🐋 ?</h2>
<p>도커는 <strong>컨테이너</strong>를 사용하여 각각의 프로그램을 <strong>분리된 환경</strong>에서 실행,관리하는 Tool</p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/6d9db38c-0ffc-4874-8d65-9c0b1b994a55/image.png" /></p>
<ul>
<li><p><strong>컨테이너</strong> : Host 컴퓨터 내 <strong>미니 컴퓨터</strong>를 의미 
  ➡️ 컨테이너는 저장공간 &amp; 네트워크(ip,port) 독립적</p>
</li>
<li><p><strong>이미지</strong> : 프로그램을 실행하기위한 <strong>모든 정보(설치옵션,설치과정,버전정보등)</strong></p>
</li>
</ul>
<ul>
<li><strong>Docker 다운로드</strong> <a href="https://myanjini.tistory.com/entry/%EC%9C%88%EB%8F%84%EC%9A%B0%EC%97%90-%EB%8F%84%EC%BB%A4-%EB%8D%B0%EC%8A%A4%ED%81%AC%ED%83%91-%EC%84%A4%EC%B9%98">윈도우에서 docker 다운로드 참고 사이트</a></li>
</ul>
<hr />
<h2 id="이미지-다운로드">이미지 다운로드</h2>
<ul>
<li><p><strong>Nginx</strong> 이미지 다운받기 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/e87c3885-68ca-4335-81a6-1a701277f9ab/image.png" /></p>
</li>
<li><p>TAG : 버전 </p>
</li>
<li><p>CREATED : 회사에서 Nginx 만든 날짜 </p>
</li>
</ul>
<h2 id="이미지-조회삭제">이미지 조회/삭제</h2>
<h3 id="에러1업로드중">에러1<img alt="업로드중.." src="blob:https://velog.io/7cf24e42-ac11-4de2-9f9e-e84d33a911d4" /></h3>
<p><strong>Error response from daemon: conflict: unable to delete 5ed8fcc66f4e (must be forced) - image is being used by stopped container 232a1c5444bf</strong>
➡️ <em>컨테이너에서 사용하고 있지 않은 이미지만 삭제 가능</em> </p>
<blockquote>
<p> 만약 삭제하려면 강제로 삭제해야함 
<strong>docker image rm -f id일부만써도가능</strong> <br />
컨테이너에서 사용하고 있지 않은 이미지만 전체 삭제
<strong>$ docker image rm $(docker images -q)</strong> <br />
컨테이너에서 사용하고 있는 이미지를 포함해서 전체 이미지 삭제
<strong>$ docker image rm -f $(docker images -q)</strong></p>
</blockquote>