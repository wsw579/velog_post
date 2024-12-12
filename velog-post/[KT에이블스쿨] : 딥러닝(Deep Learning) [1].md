<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/8ce58455-26e8-4e8d-a626-e5fe26bb7649/image.png" /></p>
<blockquote>
<p><strong>미프2차가 끝나고 벌써 딥러닝 강의시작 ! 🫢 
파이썬기초 배우고 데이터처리한게 엊그제 같은데 벌써 딥러닝이라니 .. 
kt에이블스쿨 강의듣기전에 AICE자격증 공부한적이 있어서 책을 가지고 있는데 그때는 어려웠던 내용이 한 달 조금 넘게 강의를 듣고나니까 이제 무슨내용인지 다 알겠고 할만하다는 느낌이 드는것으로보아 한 달 동안 열심히 했고 많이 성장했구나 느낄 수 있었다. 다음주는 또 미니프로젝트 3차 🌟 미니프로젝트 할때 조금 긴장도하고 쉬지도않고 열심히 하다보니 수업들을때보다 힘들기는 하지만 조원들과 의견을 나누고 몰랐던부분을 알게되고 빠르게 성장할 수 있어서 재밌기도 한 시간이다. 다음주 미니프로젝트3차도 화이팅 .. ! 💚</strong></p>
</blockquote>
<br /> 

<h1 id="📌-딥러닝-deep-learning">📌 딥러닝 (Deep Learning)</h1>
<br /> 

<h4 id="✅-딥러닝-모델">✅ 딥러닝 모델</h4>
<ul>
<li>** 모델 : 데이터로부터 패턴을 찾아 수학식으로 정리한 것 
모델링 : 오차가 적은 모델을 만드는 과정 **</li>
</ul>
<h4 id="✅-딥러닝---학습">✅ 딥러닝 - 학습</h4>
<pre><code>model.fit(x_train,y_train) 하는 순간  

단계1 ) 가중치 할당 (초기값은 랜덤) 
단계2 ) 예측시작 
단계3 ) 오차계산  (=&gt; feed-forward = forward propagation) 
단계 4) 오차를 줄이는 방향으로 가중치 조정 : (=&gt; back propagation : 오차에대한 역전파)  
가중치조정 -&gt; learning rate , epoch , batch_size 
단계 5) 다시 단계1로가서 반복 
</code></pre><blockquote>
<p>** 오차 역전파는 파라미터 업데이트를 위해 하는것이다 **</p>
</blockquote>
<h3 id="📌-hidden-layer">📌 Hidden Layer</h3>
<h4 id="✅-hidden-layer-구조">✅ hidden layer 구조</h4>
<ul>
<li>layer 여러개 [ ] 리스트로 입력 </li>
<li>activation = 'relu' 필요</li>
</ul>
<blockquote>
<ul>
<li>feature space 가 hidden layer 로 새롭게 변환된다고 말한다 </li>
</ul>
</blockquote>
<ul>
<li>최근엔 기울기소실문제로 시그모이드 활성화함수를 사용하지않는다  </li>
</ul>
<h3 id="📌-활성화-함수-activation-function">📌 활성화 함수 (Activation Function)</h3>
<ul>
<li><p>** 선형모델을 비선형모델로 변환해 복잡한 학습을 시킴 **</p>
</li>
<li><p>** 인공 신경망에서 입력을 처리하여 출력으로 변환하는 중요한 역할 **</p>
</li>
</ul>
<br />

<h3 id="🚨❓-궁금한점-추가---̀-ω-́-✧">🚨❓ 궁금한점 추가  ( •̀ ω •́ )✧</h3>
<h4 id="🚨--가중치를-쌓았을때-왜-선형모델-인가-">🚨  가중치를 쌓았을때 왜 선형모델 인가 ?  <img alt="" src="https://velog.velcdn.com/images/victoryone/post/8ff5ddbf-dd95-4aae-9e29-3f1d905853aa/image.png" /></h4>
<p>그래서 비선형성을 부여하려면 각 층 사이에 <strong>활성화 함수(Activation Function)</strong>와 같은 비선형 요소가 필요하다. 활성화 함수는 비선형 변환을 제공하여, 선형적이지 않은 복잡한 패턴을 학습할 수 있도록 해주고 대표적인 활성화 함수는 ReLU, Sigmoid, Tanh 등이 있다. </p>
<h4 id="🚨-평균오차-의미">🚨 평균오차 의미  <img alt="" src="https://velog.velcdn.com/images/victoryone/post/04b61c67-1cdc-41b3-b413-ef7163cd3a30/image.png" /></h4>
<ul>
<li>판매량이 1000개 단위로 기록된 <strong>target(목표값)</strong>이 있고, <strong>평균 오차(Mean Error, ME 또는 Mean Absolute Error, MAE)</strong>가 1이라면, 여기서의 &quot;1&quot;은 1000개의 오차를 의미합니다. 즉, 예측값과 실제 판매량 사이의 차이가 평균적으로 1000개라는 뜻입니다.</li>
</ul>
<h4 id="🚨-mape-값이-터무니없이-큰-이유는-">🚨 mape 값이 터무니없이 큰 이유는 ?  <img alt="" src="https://velog.velcdn.com/images/victoryone/post/94e28305-cfeb-4c8d-ab87-7fddcfdb51cd/image.png" /></h4>
<h4 id="🚨-딥러닝에서-w0-가중치의-의미">🚨 딥러닝에서 w0 가중치의 의미 <img alt="" src="https://velog.velcdn.com/images/victoryone/post/b3231d56-630d-48d9-af20-f13ba3944d09/image.png" /></h4>
<h4 id="🚨-pred--05">🚨 pred &gt;= 0.5 <img alt="" src="https://velog.velcdn.com/images/victoryone/post/a6537fee-b2bf-47f0-b754-c2cb76a62c22/image.png" /></h4>
<ul>
<li>이 코드는 예측값(pred)이 0.5 이상인 경우를 1로, 0.5 미만인 경우를 0으로 분류한다는 의미이다. 이를 통해 확률값으로 이루어진 예측값들을 0 또는 1의 이진 분류값으로 변환하는 과정이며 보통 로지스틱 회귀나 이진 분류 문제에서 사용한다.</li>
</ul>
<h4 id="🚨-분류모델에서-loss-fuction---binary_crossentropy">🚨 분류모델에서 loss fuction  = 'binary_crossentropy' <img alt="" src="https://velog.velcdn.com/images/victoryone/post/51f4a595-1923-4895-9652-92223fab85e0/image.png" /></h4>
<h4 id="🚨-이진분류에서-하이퍼파라미터튜닝">🚨 이진분류에서 하이퍼파라미터튜닝</h4>
<blockquote>
<p> ** columns = 53 이여서 노드수 조금 늘렸더니 ... ** 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/ff5842a7-1640-4285-a56e-031ef46a6674/image.png" /></p>
</blockquote>
<ul>
<li>원래 모델이 더 복잡했는데 (노드수가 더 많았음) dl_histroy_plot 결과가 굉장히 안좋았다 .. 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/480b2f55-4619-4e2d-b82a-3be46076e4f3/image.png" /> <br /><ul>
<li>그래서 노드수 , epoch , learning rate 더 조정했는데도 
ㅎㅎㅎ. .과적합 .. ! 
사실 이정도로 과적합될지 몰랐는데 .. 여러번 노드수랑 epochs 조정해 과적합을 피했다 !  
![]
(<a href="https://velog.velcdn.com/images/victoryone/post/c60dd6e8-8240-4070-94ee-d67dfcbae501/image.png">https://velog.velcdn.com/images/victoryone/post/c60dd6e8-8240-4070-94ee-d67dfcbae501/image.png</a>)</li>
</ul>
</li>
</ul>
<ul>
<li>binary_crossentropy 와 accuracy 상관관계 </li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/3dab3697-2e66-482e-9c01-6027b556537f/image.png" />
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/05090410-3000-461b-be59-75696cb5b71e/image.png" /></p>
<h3 id="📌-학습곡선">📌 학습곡선</h3>
<ul>
<li><p>학습곡선으로 정답을 알 수 없지만 학습데이터가 학습이 잘 되었는지 알 수 있다.</p>
<blockquote>
<p>** 바람직한 학습곡선**
<img alt="바람직한 학습곡선" src="https://velog.velcdn.com/images/victoryone/post/7cbf6694-11c5-4669-9ea7-3243cc6586b6/image.png" /></p>
</blockquote>
</li>
<li><p>초기에 오차 확 줄고 오차 하락이 꺾이면서 점차 완만해짐</p>
</li>
</ul>
<h3 id="📌-다중분류-multi-class-classification">📌 다중분류 (multi-class classification)</h3>
<h4 id="✅-다중분류-">✅ 다중분류 ?</h4>
<ul>
<li>** 다중분류는 Output Layer가 n개이상을 뜻한다. **</li>
<li>** Output Layer의 node 수는 y의 범주 수와 같다. **</li>
<li>** class 수 = y의 범주 수 = output layer 노드 수 **</li>
</ul>
<h4 id="✅softmax">✅Softmax</h4>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/ddb4fe6c-4f08-4ce2-bdf8-699e8216f26a/image.png" /></p>
<ul>
<li><p>다중분류 활성화함수 (Activation Function)</p>
</li>
<li><p>확률로 변경해 출력하고 확률 총합은 1이다.</p>
</li>
<li><p>요동치는 그래프 
학습결과 그래프가 처음보다 더 부드럽게 나왔는데 정확도는 떨어졌습니다. 학습결과그래프가 요동치는건 정확도에 큰 관계가 없나요 ? </p>
</li>
<li><p>요동치는이유 : learning_rate 가 커서 그렇다 !</p>
</li>
<li><p>그런데 learning_rate를 줄이면 보폭이 줄어드니까 epochs를 늘려야한다 : 보폭이 주니까 걸음수가 늘어나야함 </p>
</li>
<li><blockquote>
<p>그렇지만 이건  y값이 loss  이므로 부드럽게 내려간다고 정확도가 좋아진다는것은 알 수 없다 ! </p>
</blockquote>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/0705335f-6c03-482b-b5d2-cf026deeb661/image.png" /></p>
<ul>
<li><p>1인데 2로 예측 - 이런거보면 크게 벗어나진않았다 ! , 그러므로 confusion_matrix 를 같이봐야한다.</p>
</li>
<li><p>0이 많은 데이터는 주로 학습,분석이 아니기때문에 소외될수있다. -&gt; 그러면 정밀도나 재현도 , 정확도가 떨어질수있다. </p>
</li>
</ul>