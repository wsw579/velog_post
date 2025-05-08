<h2 id="컨테이너-로그-조회">컨테이너 로그 조회</h2>
<ul>
<li>docker run nginx 실행시 보였던 화면
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/0e28df31-36b9-4fe3-b531-267adb88c300/image.png" /></li>
</ul>
<p>nginx가 foreground 실행이라 화면에 로그가 보였다.
background 실행시 로그 조회 방법</p>
<ul>
<li>docker logs 컨테이너id </li>
</ul>
<p>마지막 10줄만</p>
<ul>
<li>docker logs --tail 10 컨테이너id</li>
</ul>
<p>실시간 로그 조회 </p>
<ul>
<li>docker logs -f 컨테이너id</li>
</ul>
<p>실시간 로그 조회 + 이전 로그는 조회 X </p>
<ul>
<li>docker logs -tail 0 -f 컨테이너 id </li>
</ul>
<h2 id="실행되는-컨테이너-내부-접속">실행되는 컨테이너 내부 접속</h2>
<ul>
<li>docker exec -it 컨테이너id bash</li>
<li><ul>
<li>bash 환경으로 접속 (bash: 리눅스,macOS에서사용되는 터미널)</li>
</ul>
</li>
<li>-- 내부 환경에서 나오려면 exit </li>
</ul>
<h2 id="docekr에서-redis-실행">Docekr에서 Redis 실행</h2>
<ul>
<li>docker run -d redis </li>
<li><ul>
<li>Tag 입력 안했으니까 최신버전 다운</li>
</ul>
</li>
<li>-- Redis port 6379 </li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/6034c39c-8dd5-4296-a55d-71c7d9920dfe/image.png" /></p>
<ul>
<li>docker run -d -p 6379:6379 redis 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/5afc37c2-05f5-4846-85d6-08add7d1072f/image.png" /></li>
</ul>
<p>위 그림 형태로 접속중</p>
<h3 id="reids-내부-접속">Reids 내부 접속</h3>
<ul>
<li>docker exec -it 컨테이너id bash</li>
<li>ls - 폴더없으면 cd.. 뒤로 가보기 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/35b4378f-710c-431d-aaee-74ef1f0db5b2/image.png" /></li>
<li>redis-cli : redis 접속하는 명령어 </li>
</ul>
<h2 id="docker-volume">docker volume</h2>
<ul>
<li><p>docker를 사용하면 컨테이너로 특정 프로그램을 띄울 수 있다.
하지만 도커는 프로그램에 기능이 추가 될 때 <strong>기존 이미지르 삭제하고 새로운 이미지를 만들어서 재실행</strong>한다. 이때 내부에있던 데이터도 같이 삭제되므로 MySQL같은 데이터베이스를 저장시 문제가 된다. 이때 사용하는 개념이 볼륨이다. </p>
</li>
<li><p><strong>docker volume</strong> 은 도커 컨테이너에서 <strong>데이터를 영속적</strong>으로 저장하기위한 방법이다.
컨테이너의 저장공간이 아닌 <strong>호스트의 저장공간</strong>을 공유해서 사용하는 방법이다. </p>
</li>
</ul>
<hr />
<p>*<em>mysql 실행 *</em> </p>
<blockquote>
<p>_docker run - p 3306:3306 -d mysql _
<br />mysql port : 3306 </p>
</blockquote>
<p>mysql을 설치했던 사람들은 아마 이미 실행중이라고 뜰 수 있다. 
그럼 현재 실행되고 있는 mysql을 중지시켜준다.</p>
<blockquote>
<ul>
<li>window<br />sudo lsof -i:3306 ➡️  현재 실행되는 mysql 조회<br />sudo kill pid번호 ➡️ 강제 종료 </li>
</ul>
</blockquote>
<blockquote>
<ul>
<li>mac 
시스템 설정에서 mysql 끄기 </li>
</ul>
</blockquote>
<h4 id="현재-문제점---컨테이너-내-mysql과-db데이터-따로-저장되어있어서-컨테이너를-삭제시-db데이터도-삭제됨">현재 문제점 :  컨테이너 내 MySQL과 DB데이터 따로 저장되어있어서 컨테이너를 삭제시 DB데이터도 삭제됨</h4>
<p>mysql 내 데이터베이스 mydb 만들고 다시 삭제 후 보면 mydb db는 없어졌다.</p>
<h4 id="해결방법--볼륨-사용">해결방법 : 볼륨 사용</h4>
<blockquote>
<p> pwd ➡️ 현재 위치 조회 <br /><br /> ➡️ docker 설정하는 법 : <a href="https://hub.docker.com/_/mysql">https://hub.docker.com/_/mysql</a> <br /> 📢 mysql 설정시에는 password를 설정해야 이미지가 다운 및 실행이된다. <br />
<strong>run - e MYSQL_ROOT_PASSWORD=1234 -d -p 3306:3306 -v '&quot;C:\Users\rmflt\Downloads\dodev\docker-mysql\mysql_data&quot;'</strong> (여기까지 호스트컴퓨터폴더경로)
<strong>:/var/lib/mysql</strong> (컨테이너 내 mysql 저장된 경로) 
<strong>mysql</strong> (이미지 이름)</p>
</blockquote>
<p>docker volume 생성된다.</p>
<h4 id="윈도우환경에서--mysql-password-설정하기">윈도우환경에서  mysql password 설정하기</h4>
<ul>
<li>이때 주의할 점은 mac/Linux환경에서는 pwd 조회한 경로를 바로 복사붙여넣기 해도되지만
윈도우환경에서는 ( / ) 슬래시가 아닌 ( \ ) 백슬래시로 표시된다. 따라서 '&quot; &quot;' 위 예시처럼 호스트 컴퓨터 폴더경로를 이렇게 해줘야한다. 아니면 모두 슬래시로 변경하든가  </li>
</ul>
<hr />
<h2 id="docker-volume-확인">docker volume 확인</h2>
<blockquote>
<ol>
<li>mysql로 접속 <br /></li>
</ol>
<p>** docker exec -it [컨테이너id] bash
mysql -u root -p 
password 입력 = 1234 **</p>
</blockquote>
<blockquote>
<ol start="2">
<li>새로운 db 생성하기 </li>
</ol>
<p>*<em>show databases; ➡️현재 존재하는 데이터베이스 조회
create database mydb; ➡️ mydb 디비 생성하기 *</em></p>
</blockquote>
<blockquote>
<ol start="3">
<li>현재 docker 삭제 <br />
exit로 mysql컨테이너에서 나오기 
현재 mysql 컨테이너 삭제 
docker rm -f [컨테이너id]</li>
</ol>
</blockquote>
<blockquote>
<ol start="4">
<li>다시 docker volume 생성 <br /></li>
</ol>
<p><strong>run - e MYSQL_ROOT_PASSWORD=1234 -d -p 3306:3306 -v '&quot;C:\Users\rmflt\Downloads\dodev\docker-mysql\mysql_data&quot;'</strong> (여기까지 호스트컴퓨터폴더경로)
<strong>:/var/lib/mysql</strong> (컨테이너 내 mysql 저장된 경로) 
<strong>mysql</strong> (이미지 이름)</p>
</blockquote>
<p>** 📢 아까 처럼 mysql 컨테이너에 접속해서 데이터베이스를 조회하면 아까 만든 mydb 디비가 조회된다. **</p>
<blockquote>
<p>📢 docker volume password 설정시 주의할 점 
볼륨을 사용하면 
처음에 만든 데이터베이스의 password가 저장된다. 
따라서 새로 데이터베이스를 만들어도 패스워드는 똑같다. 새로 덮어쓰지 않으므로 만약에 새로운 password를 설정하고 싶다면 현재 데이터가 저장된 <strong>폴더를 삭제</strong>하고 <strong>이미지를 다시 생성</strong>해야한다.</p>
</blockquote>
<blockquote>
<p>🚨 *<em>주의할 점 : 호스트 컴퓨터 폴더 생성유무 *</em> <br />
*<em>1) 폴더 생성되어 있을 때 *</em>
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/1d96924b-f224-4a71-b22b-83f50d1db7d3/image.png" />
*<em>2) 폴더 생성 안되어 있을 때 *</em>
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/2cdcdfc4-8ba4-4790-bb27-1fb408215b05/image.png" /> 
따라서 미리 존재한 디렉토리를 삭제하고 저장해야한다. </p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/48191492-160e-4166-b27b-bad255f58995/image.png" /></p>
<ul>
<li>위 그림에서 보이듯이 호스트 컴퓨터의 저장공간과 컨테이너 저장공간을 공유하는 것을 볼 수 있다.</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/ef2fc309-2ffa-4976-a022-954ce7df3479/image.png" /></p>
<ul>
<li>먼저 호스트 컴퓨터에 empty.txt 저장하기</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/b2b23f3f-7264-43ff-98dc-cec9d14f9fb5/image.png" /></p>
<ul>
<li>그리고 docker 내부 접속시 똑같이 empty.txt가 생성되어 있는것을 볼 수 있다. </li>
</ul>