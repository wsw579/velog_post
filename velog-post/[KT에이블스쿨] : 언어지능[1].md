<blockquote>
<p><strong>또 새롭게 시작하는 에이블스쿨 
이번주는 언어지능을 공부합니다 ! 
자연어처리는 추천시스템 , 챗봇, 알고리즘 , 인터넷뉴스 요약 등 우리의 실생활에서 다양하게 사용되고 있더라고요. 
이번 언어지능파트 강사님은 현재 고려대 교수님이신 김중헌 교수님.
확실히 현재 대학에서 강의하고 있으셔서 그런지 😆😆 학과때 교수님수업 듣는 것 같았습니다. 
현업에서 많이사용하는 기술이라든지 현재 딥러닝 , 교수님이 연구하시는 양자컴퓨터 등 다양한 분야에대해서도 말해주셔서 수업이 너무 재밌었습니다 ( ͡° ͜ʖ ͡°)</strong></p>
</blockquote>
<br />

<hr />
<br />

<h2 id="📌-tf---idf">📌 TF - IDF</h2>
<p><strong>▶ TF(Term Frequency) **  
**▶ IDF (Inverse Document Frequency)</strong> </p>
<hr />
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/31a83282-ebd6-48b7-aa56-27a34d0959a0/image.png" /></p>
<ul>
<li><p><strong>연설문에서 대표할 수 있는 16개 단어를 추출할때 고려할 것</strong></p>
<blockquote>
<p>*<em>1. TF = 많이 나와야한다  <br /> 2. IDF = 특정 문서에 자주 등장하지만 전체 문서에서는 드물게 나와야한다. *</em></p>
</blockquote>
</li>
<li><p>** IDF 예시 설명 **</p>
<ul>
<li>100개의 연설문을 보고 in 은 무조건  100개 연설문에서 다 보일 것 이다 .
100개의 연설문을 보고 hope은 100개 연설문 중 1개에서 보인다. 그렇다면 hope는 이 연설문을 대표하는 단어가 된다. <br /> 
### ✔️ TF - IDF = TF(t , d) * IDF (t , D) </li>
</ul>
</li>
<li><p>D = document 
TF - IDF 는 스칼라 값 </p>
<br /> 

</li>
</ul>
<h2 id="📌-단어표현">📌 단어표현</h2>
<p>▶ <em>** Word Representation, Word Embedding, Word Vector**</em></p>
<hr />
<p>** ⬛  단어표현 : 텍스트가 얼마나 유사한지 표현하는 방식 **</p>
<ul>
<li><p>텍스트를 모델에 넣어서 처리할때 벡터의 형태로 표현한다. 
하나의 벡터는 그 단어를 표현하는 유니크한 값이다. </p>
</li>
<li><p>기본적으로 데이터 표현을 원핫인코딩으로 한다.</p>
<blockquote>
<p>하나만 1 (1개만 hot하다 ) 나머지는 0
그러나 원핫인코딩은 자연어 단어 표현엔 부적합하다. </p>
</blockquote>
</li>
<li><p><em>왜냐하면 10만개의 단어가 있다면 <em>100000000...000</em> 이 표현을 10만개를 만들어야한다.*</em>
그런데 다음날 신조어가 1개 생긴다고 가정하면 10만1개를 또 만들어야한다. </p>
</li>
<li><p><em>그리고 이 표현은 단어의 의미나 특성을 표현할 수 없다. 
모든단어가 1,0 이 많다 = 고차원 = 사이즈가 크다를 의미하고 , 많은 것중에 1이 한 개 = 저밀도를 의미한다*</em>.</p>
</li>
</ul>
<br /> 

<h2 id="📌-유사도-판단">📌 유사도 판단</h2>
<hr />
<p>• 텍스트를 벡터화한 후 벡터화된 각 문장간의 유사도를 측정하는방식
• <strong>대표적인 유사도 측정방식: 코사인 유사도</strong> , 자카드 유사도 , 정확도 등등 .. </p>
<ul>
<li>** 자카드 유사도 **</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/f1a29559-2bb9-42d1-a285-66346fc47e60/image.png" /></p>
<ul>
<li>*<em>정확도 *</em></li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/1bab07ae-5eb4-4951-b33f-40ed378b6824/image.png" /></p>
<blockquote>
<p> *<em>자카드 유사도 &amp; 정확도 차이 *</em></p>
</blockquote>
<ul>
<li>** array가 이렇게 있다면 [ 1, 3 ,2 ] [ 1, 4 ,5 ] **<ul>
<li>자카드유사도와 정확도는 같은 array에 따라 각각 1/5 , 1/3 다른결과 나온다.</li>
<li>5개 값중 1개가 같으므로 1/5 (교집합)</li>
<li>정확도는 [ 1, 3 ,2 ] [ 1, 4 ,5 ] 일때 세로로 비교하면 1/3  </li>
</ul>
</li>
</ul>
<ul>
<li>** 코사인  유사도 **</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/ecc48402-a72d-4efb-915b-ae2704e4ffed/image.png" /></p>
<ul>
<li>벡터개념으로 보면, 
0도 → 코사인 0은 값이 1 (같은방향,관계가있음) , 
90도 → 코사인 90은 값이 0 (아무관계없음) , 
180도 → 코사인 180은 값이 -1 (가장 큰 반대관계) </li>
</ul>
<blockquote>
<p>💡 *<em>print ( vector_result ) 결과 의미 *</em> <br />
(0, 6)    0.5
  (0, 0)    0.5
  (0, 1)    0.5
  (0, 3)    0.5
  (1, 4)    0.5773502691896257
  (1, 2)    0.5773502691896257
  (1, 5)    0.5773502691896257</p>
</blockquote>
<ul>
<li><strong>TfidfVectorizer가 sentence 내 각 단어를 알파벳 순서 또는 가나다 순서로 정렬하여 인덱스를 부여</strong>
예를 들어, ['KT', '강의', '날입니다', '언어지능을', '예정입니다', '오늘은'] 순서는 사전 순으로 정렬된 단어 목록이다.</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/f59ca04e-423c-4401-8cf2-0a540b488140/image.png" /></p>
<ul>
<li>문장의 TF-IDF 벡터화
vector_result = vector.fit_transform(sentence) 코드가 문장을 TF-IDF 벡터로 변환한다.
이때, 각 문장의 단어들은 위에서 지정한 인덱싱 순서에 따라 벡터화된다.
vector_result 출력 시 나타나는 값은 단어 인덱스와 그 단어의 TF-IDF 가중치를 보여준다.
따라서, vector_result를 출력하면 TfidfVectorizer가 문장을 벡터화한 결과로, 사전 순서로 인덱싱된 단어들에 대한 TF-IDF 값이 표시된다.</li>
</ul>
<br />

<h2 id="📌-비지도학습">📌 비지도학습</h2>
<hr />
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/c260f667-e3e9-4a3f-8a8f-4b38afa182a2/image.png" /></p>
<ul>
<li><p>머신러닝 = 아무것도 모르는 모델에 데이터를 하나씩 학습시켜서 발전시키는 것 이다. 
예를들어, 아무것도 모르는 아기가 있는데 아기에게 말을 하나씩 알려주면서 발전시키는 것 이다. 
0 -&gt; 100까지 </p>
</li>
<li><p>AI = 인공적으로 지능을 만들어준다. 즉 , 논리를 만들어줌 
처음부터 100을 만들어놓고 어떤 질문이 논리에 맞는지 확인한다.  </p>
</li>
<li><p>머신러닝</p>
<ul>
<li>Supervised Learning : data와 label이 존재 , 지도학습 =&gt; 발전시키면  DL</li>
<li>Unsupervised Learning : data만 존재 ,비지도학습 
ex) 아이에게 펜을 주면서 먹지말라고 함(label을 줌) - 하지만 아이는 이해하지못함 - 그래서 펜을 입에문다 - 펜은 여태 먹었던 이유식과 달라(=유사도판단) - 먹지않음</li>
<li>벡터를 만드는 것 = label 만드는 것 </li>
</ul>
</li>
</ul>
<ul>
<li><strong>Classification *<em>: Supervised Learning vs. *</em>Clustering</strong> : Unsupervised Learning
<br /><br /><h2 id="📌-데이터-표현">📌 데이터 표현</h2>
</li>
</ul>
<hr />
<ul>
<li>*<em>discrete vs continuse *</em><blockquote>
<p>온도가 몇 ? 38.1 도라고 대답 실제 38.11111111191293 ... 이라도 대답은 인간이 알아듣는 기준까지만 한다.</p>
<br />
</blockquote>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/28aaeb97-0bae-4cb6-b592-518bafbea2fe/image.png" /></p>
<ul>
<li><p>Data matrix = object by feature 구조 </p>
</li>
<li><p>Distance matrix = 거리 행렬 = dissimilarity matrix = 거리가 크면 클 수록 비슷하지않다 
d(1,2) : 1에서부터 2까지 거리 = d(2,1) = object<br />거리는 유클리디언 거리 식을 사용 </p>
</li>
<li><p>** 거리 식 종류  **</p>
</li>
</ul>
<ol>
<li>유클리디언 거리 = 대각선 </li>
<li>맨하탄 거리 = 직선 </li>
<li>민코스키 거리 Minkowski Distance = 유클리디언 거리와 맨하탄 거리 둘 다 나타낼 수 있는거리 
p 값에 따라 달라짐 </li>
</ol>
<blockquote>
<p>d(x,y) = (|x1-y1|^p+(|x2-y2|)^p+.... |x?-y?|^p)^1/p
p=1 일때 맨하탄 거리 
p =2 일때 유클리디언 거리 </p>
</blockquote>
<br />

<h2 id="📌-cosine-measure">📌 Cosine Measure</h2>
<hr />
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/7307961c-ce38-4966-a5b7-8452cf0331e6/image.png" /></p>
<ul>
<li><p><strong>벡터의 곱셈</strong>
1) 내적 ( 결과가 스칼라) 
2) 외적 ( 결과가 벡터) -&gt; 3차원에서만 존재 -&gt; 그래픽스에서 사용 </p>
</li>
<li><p>같으면 1 , 다르면 -1 
d(x,y) = 1 - cos(x,y) -&gt; 1일때는 결과가 0 , 다를때 -1 -&gt; 1-(-1) = 2 완전히 차이가 난다</p>
</li>
</ul>
<br />

<ul>
<li>*<em>Clustering *</em></li>
</ul>
<p>1) K-means </p>
<blockquote>
<p>2개의 clustering을 하고싶으면 , 랜덤으로 2개선택해서 군집을 이루는데 대표가 바뀌지 않을때까지 반복한다.
단점 ㅣ 초기값에 따라 수렴이 느릴 수 있다 , k가 뭔지모른다.  </p>
</blockquote>
<p>2) KNN  (k-nearest-neighbor)</p>
<blockquote>
<p>k =3  ,  가장가까운 3개를 고름 
c 근처에 a 2개 , b 1개가 가깝다면 c는 a가 된다 
단점 | 이상치에 민감하다. </p>
</blockquote>
<p>3) 앙상블 </p>
<p>4) word embedding 
단어 간 <strong>코사인 유사도(cosine similarity)</strong>를 통해 의미적 관계를 평가하는 것 </p>
<ul>
<li>Word2Vec
x,y,z, 모두 90도라 관계가 없고 , 처리가 어려울때 단어간 코사인유사도를 사용해 벡터화 하기 </li>
</ul>
<hr />
<br />

<h2 id="📌-추천시스템">📌 추천시스템</h2>
<hr />
<br />

<p><strong>추천시스템 배경</strong></p>
<ul>
<li>파레토 법칙 : 상위 20%가 80% 가치를 창출한다. </li>
<li>롱테일 법칙 : 하위 80%의 다수가 상위20%보다뛰어난가치를창출한다.</li>
</ul>
<blockquote>
<ul>
<li>모순된 두 개념을 가지는 추천시스템 
일반적으로 파레토 법칙을 통해 상위 인기 상품을 우선 제공하여 높은 만족감을 느낄 수 있고, 그 이후 롱테일 법칙을 통해 다양한 사용자에게 맞춤형 콘텐츠를 제시한다.</li>
</ul>
</blockquote>
<p>*<em>추천시스템 정의 *</em></p>
<ul>
<li>사용자의 관심사와 선호도를 파악해 그에 맞는 상품이나 콘텐츠를 자동으로 예측하고 제공하는 시스템이다. </li>
</ul>
<blockquote>
<ul>
<li>사용자 행동 이력(<strong>상품 구매, 콘텐츠 시청, 별점 등</strong>) , 
사용자 간의 관계(<strong>유사한 관심사를 가진 다른 사용자의 행동을 참고하여, 사용자들이 비슷하게 선호할 만한 아이템을 추천</strong>), 
상품 간 유사도, 
사용자 컨텍스트(<strong>성별, 연령대, 위치 등</strong>) 같은 데이터를 기반으로, 개인화된 추천을 수행한다.</li>
</ul>
</blockquote>
<p>💡  이러한 사용자 행동이력은
<strong>User Behavior Activity Log</strong>에 저장된다. 사용자가 웹사이트나 앱에서 어떤 활동을 했는지 서버에 실시간으로 전송되고, 이를 저장하여 분석에 사용한다. </p>
<p>🔎 쿠팡에서 나이키 신발을 사고 페이스북에 들어가면 페이스북에서 나이키신발 ad가 보인다 → 쿠팡 ad서버로 붙는 형태 
<br /></p>
<h3 id="✔️-추천-시스템-알고리즘">✔️ 추천 시스템 알고리즘</h3>
<h4 id="⬛-협업-필터-collaborative-filtering">⬛ 협업 필터: Collaborative Filtering</h4>
<p>▶ 유사도 측정 </p>
<h4 id="⬛-컨텐츠-기반-필터-content-based-filtering">⬛ 컨텐츠 기반 필터: Content-Based Filtering</h4>
<p>▶ 속성에 기반해 유사 속성 아이템 추천
<br /></p>
<blockquote>
<ul>
<li><strong>협업 필터링과 콘텐츠 기반 필터링의 차이점</strong>
협업 필터링은 여러 사용자의 <strong>데이터로부터 유사성을 파악</strong>하여, 비슷한 사용자가 좋아한 아이템을 추천하고 
콘텐츠 기반 필터링은 <strong>아이템 자체의 특성에 집중</strong>하여, 유사한 속성을 가진 다른 아이템을 추천한다. </li>
</ul>
</blockquote>
<ul>
<li>협업 필터 예시 <blockquote>
<p>WOO 사용자가 넷플릭스를 주로 &quot;로맨스&quot; , &quot;액션&quot;만 보고 신규콘텐츠로 &quot;다큐멘터리&quot; 가 들어온다면 헙업필터방식은 코사인 유사도를 기반으로 하기때문에 이 신규콘테츠를 추천하지 않는다.
이런한 문제점으로 [1] 알고리즘 고착화 [2] 추천의 유한성이 있다. </p>
</blockquote>
</li>
</ul>
<ul>
<li>컨텐츠기반 필터 예시<blockquote>
<p>다양한장르의 작품에 출연하는 조승우. 조승우가 나오는 작품만 볼때 컨텐트기반 필터링을 하면 로맨스&amp;액션 작품 中 조승우가 나오는 작품을 추천해준다. </p>
</blockquote>
</li>
</ul>
<p>💡 최근에는 협업필터와 컨텐츠기반필터를 같이 사용한다.
<br />
<strong>추천알고리즘 단점</strong></p>
<ul>
<li><p>CF </p>
</li>
<li><p><em>gray sheep*</em> :  취향이 없고, 평가가 일관적이지 않은 사람들에겐 도움이 안된다.
💡 별점 시스템이 gray sheep 이슈가 있다보니, 몇 년전부터 Good/Bad 형태로 많이 변경되었다. (ex. 넷플릭스평점, 유튜브 좋아요 등) </p>
</li>
<li><p><em>초기 사용자*</em> 에 대해선 데이터가 없다보니 믿을만한 추천을 하기 어렵다.</p>
</li>
<li><p>CBF 
카테고리 한계 :** 사용자의 선호도 &amp; 취향을 특정 단어로 표현하기 어렵다. **</p>
</li>
</ul>
<hr />
<h2 id="💻실습-rss---기사검색--긍정부정-단어-tf">💻실습 RSS - 기사검색 + 긍정/부정 단어 TF</h2>
<p><a href="https://github.com/wsw579/TIL/blob/main/20241106">Github 링크</a></p>
<hr />
<ul>
<li>Overfitting 이슈 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/86ef8a6f-cd84-4229-a210-b1c1dd336fbe/image.png" /></li>
</ul>
<h2 id="📌-xor">📌 XOR</h2>
<ul>
<li>XOR구조 </li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/2f7023ff-e27f-46cb-9a3d-b2a0c5341b74/image.png" /></p>