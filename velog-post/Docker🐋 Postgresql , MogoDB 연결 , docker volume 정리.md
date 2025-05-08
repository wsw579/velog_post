<h2 id="postgresql">Postgresql</h2>
<p><a href="https://hub.docker.com/_/postgres">docker hub Postgresql 참고문서</a></p>
<blockquote>
<p>doceker 허브 사이트에서 이미지의 유무 확인하고 default 설정방법도 찾아볼 수 있다.</p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/703f332c-f303-4c76-b2aa-2e6eb8b0680a/image.png" /></p>
<blockquote>
<p>Postgresql 기본 port : 5432 
postgresql data 저장 경로 /var/lib/postgresql/data
*<em>윈도우환경에서는 호스트 컴퓨터 경로에 &quot; &quot; 붙이기 *</em> <br /></p>
</blockquote>
<br />

<h2 id="mongodb">MongoDB</h2>
<blockquote>
<p>*<em>참고로 DBever community 사용시 MongoDB 연결이 불가 ... ! <del><em>비버 귀여워서 사용하는데 배신이야 ㅜ</em></del> <br /> 몽고디비 연결하고 싶다면 DataGrip / TablePlus 대체해서 사용하세요 !  *</em></p>
</blockquote>
<p><a href="https://hub.docker.com/_/mongo">docker hub MongoDB 참고문서</a></p>
<p>MongoDB DB 접속 CLI  ➡️mongosh
DataGrip으로 test connecting </p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/ed78c960-8684-49be-976e-974c2a9a9258/image.png" /></p>
<blockquote>
<h4 id="📍-즉-docker-volume을-통해-mongodb-컨테이너를-삭제해도-호스트의-저장공간에-데이터가-저장되어-새로운-mongodb-컨테이너가-사용할-수-있다">📍 즉, docker volume을 통해 mongodb 컨테이너를 삭제해도 호스트의 저장공간에 데이터가 저장되어 새로운 mongodb 컨테이너가 사용할 수 있다.</h4>
</blockquote>
<h4 id="위-그림에서-보는듯이-docker-컨테이너-내-mongodb이미지를-호스트와-컨테이너-포트맵핑을-통해서-사용할-수-있는-것이다">위 그림에서 보는듯이 docker 컨테이너 내 mongodb이미지를 호스트와 컨테이너 포트맵핑을 통해서 사용할 수 있는 것이다.</h4>
<blockquote>
<p>** 📍docker에서 서버나 db를 연결할때 연결유무 확인방법 정리**
기본적으로 docker logs를 사용해서 조회
서버는 직접 브라우저에서 연결해보기
db는 dbever같은 프로그램으로 연결 확인 </p>
</blockquote>