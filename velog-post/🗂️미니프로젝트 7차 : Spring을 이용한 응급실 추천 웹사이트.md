<blockquote>
<p><strong>에이블스쿨 시작한지 벌써 4개월차 ...
드디어 미니프로젝트도 마지막이다. 벌써 7차 미니프로젝트라니 정말 감회가 새롭다.
시간은 빠르고 , 지금까지 배운내용도 많고 성장도 많이 했다.
특히 이번 미니프로젝트7차는 '미니' 가 아닌 정말 제대로된 하나의 프로젝트였다.
6차 fine_tuned_bert ai모델을 사용하여 위도⊙경도로 받은 위치에서 가장 가까운 병원3개를 추천받는 모델을 만들었었다. 이번에는 그 모델을 더 디벨롭시키고 , Spring을 사용해 웹사이트를 만드는 것이 미니프로젝트7차 목표이다 !!! ✨
바로 어제 미니프로젝트7차가 끝났고 우리 12조는 발표도 하게 되었다 🎉
많은분들이 우리조 결과물을 보고 칭찬을 해주어서 너무 좋았다. (감사합니다🤗)
그리고 다같이 열심히 노력해주고 잘해준 우리팀들에게 너무 고마웠다. 
한 가지 바람은 빅프로젝트에서 열심히해서 팀에 더 많은 기여를 하고 싶고 우리팀원분들에게 많은 도움이 되고싶다 ! 💚</strong></p>
</blockquote>
<ul>
<li><p>이번 미니프로젝트 7차는 개별프로젝트와 그걸 활용한 팀프로젝트 순으로 진행되었다
개별과제에서는 6차에서 했던 fine_tuned_bert모델을 사용한 코드로 통합모델을 만들어보고 , sqlite 를 사용해 DB를 만들고 함수를 이용해 DB에 통합모델을 통해 응급실병원 3곳을 추가하도록 하는 것 이 었다. 마지막으로 응급실데이터를 get 또는 post로 데이터를 받아 홈페이지에서 확인 할 수 있도록 하는 홈페이지를 만드는 것이다. </p>
</li>
<li><p>팀 별 프로젝트는 개별프로젝트에서 만든 홈페이지를 html / css 를 이용해 홈페이지를 꾸며보고 , 애저와 도커를 사용해 자동배포가 가능하도록 하고 , 마지막으로 spring과 html,css,javasript를 이용해 홈페이지에 추가기능을 만들고 배포까지 해보는 것 이 미니프로젝트 7차 목표였다.</p>
</li>
</ul>
<p>미니프로젝트 6차에서 조금 시간이 지났고 , 내가 하지않은 코드부분을 초반에 다시 이해하는데 시간이 조금 걸렸고, 처음 접해보는 get,post를 활용해 홈페이지로 보내 데이터를 출력해보는 부분에서 계속 오류가나고 많이 실행을 하다보니 지급받은 개인 api의 하루할당량을 빨리 써버려서 .. 당일에 더 실행하지못해 아쉬움도 남았었다.
이후 아쉬움에 남아서 추가공부를 더했고 개별과제에서 해결하지 못한 부분을 해결해서 너무 기뻤다. 미니프로젝트 7차가 끝나면서 며칠사이 내가 더 성장한 것 같았다 🤗✨</p>
<p>미니프로젝트 7차는 spring을 활용해 홈페이지를 구현하는 것이 key-point 였는데
우리 12조는 1. 로그인/회원가입 2. 관리자페이지 및 관리자페이지 내 DB차트,기간 3. 네이버지도API연결해 길찾기 구현 4. 문의게시판/글작성/삭제/수정/답글 5. 응급실요청시 특이사항선택 6.음성/문자 응급실요청부분 크게 보면 이렇게 추가기능을 구현했다. 모두가 노력했고 열심히 했는데 뭔가 내가 더 많이알았더라면 더 도움이 되었을텐데라는 스스로에게 아쉬움이 남았다.
그래서 미니프로젝트7차가 끝나자마자 spring과 html/css부분을 공부시작했다.</p>
<p>빅프로젝트에선 이러한 아쉬움이 남지않도록 ... !! ✨✨✨
한 달 반정도 사실 후다닥 지나갈 빅프로젝트기간동안 후회와 아쉬움이 남지않도록 열심히하고 , 같은 팀원들을 존중하고 배려하며 모두가 만족하는 빅프로젝트가 되었으면 .. 
2월달에 빅프로젝트가 끝나고 웃으면서 빅프로젝트 후기를 남기길 바라본다.</p>
<p>미니프로젝트 7차 12조 결과물을 첨부해본다 (❁´◡`❁)</p>
<ul>
<li><p>처음 페이지를 들어가면 위치요청을 한다.
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/acfd315f-bf8c-4f17-b944-0f69246c78fa/image.png" /></p>
</li>
<li><p>기본페이지 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/7562e925-a79d-40ac-9e73-a9c4619cacdf/image.png" /></p>
</li>
<li><p>문자구조요청 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/7f4016f3-2851-427d-8dcc-ec97f02fbaaf/image.png" /></p>
</li>
<li><p>로그인을 하지않으면 구조요청은 가능하지만 방문자라고 뜬다.
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/d896af8e-1c8d-4160-a87c-2134ee1b8185/image.png" /></p>
</li>
<li><p>회원가입 후 로그인하게되면 방문자가 아닌 내 이름으로 사용할 수 있다. 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/ab8f7967-9202-4e71-a28d-4baa812fdf96/image.png" /></p>
</li>
</ul>
<hr />
<ul>
<li>여기서 부턴 영상으로 </li>
<li>문자로 응급실 요청시 특이사항과 혈액형을 선택할 수 있다. </li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/9a984633-8b6b-4f99-9ae2-7a0f188208e5/image.gif" /></p>
<ul>
<li><p>요청 후 내위치에서 가장가까운 3개의 병원이 추천되고 네이버지도로 길찾기까지 지원한다.
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/e9adecd1-e514-4b58-9cb5-f02f16b16acf/image.png" />
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/d7a594fe-8561-47f2-b817-7384355723d9/image.png" />
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/55599b3e-b5da-4071-82f8-d5ccb108c832/image.png" /></p>
</li>
<li><p>음성으로 요청시 오디오파일을 첨부하는 형식으로 요청한다.
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/1ff72677-ab65-4729-813a-351589a9fff3/image.gif" /></p>
</li>
<li><p>admin(관리자)로그인 및 문의게시판 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/aa8bbc11-54d7-4f7c-be86-902d33d8d302/image.gif" /></p>
</li>
<li><p>관리자페이지이동 (admin로그인시에만 가능) 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/83091115-4706-4916-8866-45308e7abbcf/image.gif" /></p>
</li>
</ul>