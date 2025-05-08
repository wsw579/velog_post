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
<li><p><strong>이미지</strong> : 프로그램을 실행하기위한 <strong>모든 정보(설치옵션,설치과정,버전정보 등)</strong></p>
</li>
</ul>
<ul>
<li><strong>Docker 다운로드</strong> <a href="https://myanjini.tistory.com/entry/%EC%9C%88%EB%8F%84%EC%9A%B0%EC%97%90-%EB%8F%84%EC%BB%A4-%EB%8D%B0%EC%8A%A4%ED%81%AC%ED%83%91-%EC%84%A4%EC%B9%98">윈도우에서 docker 다운로드 참고 사이트</a></li>
</ul>
<hr />
<h2 id="이미지-다운로드">이미지 다운로드</h2>
<ul>
<li><strong>Nginx</strong> 
➡️ docker pull nginx : 이미지 다운받기 
➡️ docker create nginx : 컨테이너 생성 👉🏻 배치 
➡️ docker start 컨테이너ID : 컨테이너 실행  👉🏻 실행 </li>
</ul>
<p>⏩ *<em>이미지 다운 + 생성 + 실행 = docker run *</em>
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/e87c3885-68ca-4335-81a6-1a701277f9ab/image.png" /></p>
<ul>
<li>TAG : 버전 </li>
<li>CREATED : 회사에서 Nginx 만든 날짜 </li>
</ul>
<h2 id="이미지-조회삭제">이미지 조회/삭제</h2>
<h3 id="에러1">에러1</h3>
<p><strong>Error response from daemon: conflict: unable to delete 5ed8fcc66f4e (must be forced) - image is being used by stopped container 232a1c5444bf</strong></p>
<p>➡️ <em>컨테이너에서 사용하고 있지 않은 이미지만 삭제 가능</em> </p>
<blockquote>
<p> 만약 삭제하려면 강제로 삭제해야함 
** docker image rm -f id일부만써도가능** <br />
컨테이너에서 사용하고 있지 않은 이미지만 전체 삭제
** docker image rm $(docker images -q)** <br />
컨테이너에서 사용하고 있는 이미지를 포함해서 전체 이미지 삭제
** docker image rm -f $(docker images -q)**</p>
</blockquote>
<h2 id="foreground--background">Foreground / Background</h2>
<p>_Foreground : 내가 실행시킨 프로그램 내용이 화면에서 실행되고 출력되는 상태 _
_Background : 내가 실행시킨 프로그램이 컴퓨터 내부적으로 실행되는 상태 _
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/3e122958-d08b-4cf3-a68f-f4c4f66ad9c4/image.png" /></p>
<p><strong>아무것도 실행 되지않는 이유</strong> </p>
<blockquote>
<p><strong>➡️ docker run nginx  : Foreground에서 실행</strong></p>
</blockquote>
<br />

<h2 id="docker-명령어">Docker 명령어</h2>
<ul>
<li><p>docker image nginx : nginx이미지 다운받기 </p>
</li>
<li><p>docker create nginx : nginx컨테이너 생성 </p>
</li>
<li><p>docker start 컨테이너ID : nginx 컨테이너 실행  </p>
</li>
<li><p>위 세가지 합쳐놓은 명령어 - docker run </p>
</li>
<li><p>docker image rm -f id일부만써도가능 : 실행되고 있는 컨테이너 바로 삭제 </p>
</li>
<li><p>docker image rm $(docker images -q) : 컨테이너가 사용하고 있지않은 이미지 삭제 </p>
</li>
<li><p>docker rm $(docker ps -qa) : 중지된 모든 컨테이너 삭제 </p>
</li>
<li><p>docker image rm -f $(docker images -q) : 모든 이미지 삭제 </p>
</li>
<li><p>docker ps : 실행중인 전체 컨테이너 조회 </p>
</li>
<li><p>docker ps -a : 존재하는 전체 컨테이너 조회</p>
</li>
<li><p>docker image ls : 존재하는 이미지 조회  </p>
</li>
<li><p>docker run -d nginx : Background에서 nginx 실행</p>
</li>
<li><p>docker stop 컨테이너id : 컨테이너 중단</p>
</li>
<li><p>docker kill 컨테이너id : 컨테이너 강제 중단 </p>
</li>
<li><p>docker rm 컨테이너id : 중지된 컨테이너 삭제</p>
</li>
<li><p>docker rm 컨테이너id 컨테이너id 컨테이너id : 컨테이너 한 번에 여러개 삭제</p>
</li>
<li><p>docker image rm 이미지이름 : nginx(이미지이름) 이미지 삭제 </p>
</li>
<li><p>docker image rm 이미지id : 이미지 삭제 </p>
</li>
<li><p>clear : 실행화면 초기화 </p>
</li>
<li><p>docker run -d --name my-web-server nginx : 실행시키는 컨테이너에 이름 붙이기 </p>
</li>
<li><p>docker run -d -p 4000:80 nginx : 외부에서 요청된 호스트port 4000  - 컨테이너 port 80 맵핑 </p>
<br />

</li>
</ul>
<h2 id="port-맵핑">port 맵핑</h2>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/58574ff6-e77a-44d9-84cb-fa10533e2a56/image.png" /></p>
<p>컨테이너 실행 후 port 80 이라고 나와있다. 
잘 동작되고 있는지 localhost:80 실행 </p>
<blockquote>
<p>결과적으로 localhost:80 해도 아무것도 나오지않는다.
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/d5598d75-123d-4e0a-9490-0d2dea358a55/image.png" /></p>
</blockquote>
<ul>
<li>nginx가 실행되는 환경이 호스트 컴퓨터 內 컨테이너 </li>
<li>컨테이너의 port : 80 </li>
<li>호스트 port : 4000
따라서 호스트-컨테이너 port 맵핑 시켜줘야한다. 
➡️** docker run -d -p 4000[host port]:80[컨테이너 port] nginx**</li>
</ul>
<p>*<em>➡️ 이때 시크릿모드로 실행하기 캐싱으로 인하여 실제로 실행되고 있지않는데 그 이전의 데이터를 보여줄 수 있기때문에  *</em></p>
<br />

<ul>
<li>** docker run -d -p 80[host port]:80[컨테이너 port] nginx ** 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/0446eb51-29d2-4d02-9957-5de22d50860f/image.png" />
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/de38ceef-2388-44f3-8fe0-3a87fd584e40/image.png" />
맵핑 완료</li>
</ul>