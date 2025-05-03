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
<li>도커 컨테이너에서 데이터 지속적으로 저장하기 위한 </li>
<li>docker run -v</li>
</ul>