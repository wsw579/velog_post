<blockquote>
<p>다시 돌아온 한 주 ... 주말에 복습도하고 조금 쉬니까 벌써 한 주가 돌아왔 .. 
사실 딥러닝 내용이 어렵진 않지만 공부하다보면 이 부분은 왜그러지? 궁금증도 생기고 그러면 추가로 찾아보고 공부하고 코드는 많이해보고 익혀야 자동적으로 나오다보니 아는것도 계속 외워서 치다보면 시간이 훌쩍간다.. 그래서 공부계획은 또 못맞추고 🥹🥲 그래도 나아가야지 어떡해 🚶🏻‍♀️🚶🏻‍♂️🚶🏻</p>
</blockquote>
<h2 id="📌-딥러닝deep-learning-2">📌 딥러닝(Deep Learning) [2]</h2>
<h3 id="📌-성능관리">📌 성능관리</h3>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/6e0bc5bb-d9f3-4d2a-beb5-01e6c032af60/image.png" /></p>
<ul>
<li>너무 단순한 모델 ㅣ 과소적합 | train,val 성능 떨어짐</li>
<li>적절히 복잡한 모델 | 적절한 예측력 </li>
<li>너무 복잡한 모델 | 과대적합 |  train 성능높고 , val 성능 떨어짐 </li>
</ul>
<blockquote>
<p><strong>일반화 손실(Generalization Loss)은 머신러닝 모델이 훈련 데이터에서 학습한 내용을 새로운 데이터(테스트 데이터)로 얼마나 잘 일반화할 수 있는지를 나타내는 개념이다. 
쉽게말해, 모델이 훈련 데이터에 대해 잘 예측하더라도 새로운 데이터에 대해 성능이 떨어지는 현상을 말한다.</strong></p>
</blockquote>
<h4 id="✅-딥러닝-조절할-대상">✅ 딥러닝 조절할 대상</h4>
<ul>
<li>Epoch &amp; learning_rate </li>
<li>모델구조 : hidden layer 수 , node 수 </li>
<li>규제 - 미리멈춤 (Early Stopping)<pre><code>- 임의연결끊기 (Dropout)
- 가중치 규제하기 (Regularizaion) -&gt; 참고자료 </code></pre></li>
</ul>
<h4 id="✅-미리멈춤-early-stopping">✅ 미리멈춤 (Early Stopping)</h4>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/5646c51f-bb98-4dc0-af7a-a7e58df12711/image.png" /></p>
<blockquote>
<p>*<em>최종 저장된 모델은 최고 성능 모델을 쓰든 , 마지막 모델을 쓰든 크게 상관없다. 조금의차이는 크게 중요하지않기때문에 !  *</em> <br /> </p>
</blockquote>
<h4 id="✅-임의연결끊기-dropout">✅ 임의연결끊기 (Dropout)</h4>
<p> 모델저장하기 : 최종모델 저장 </p>
<ul>
<li><p>구글드라이브 연결 </p>
</li>
<li><p>중간 체크포인트 저장하기 </p>
</li>
</ul>
<h4 id="🚨-성능관리">🚨 성능관리</h4>
<ul>
<li>✅ 성능에 가장 많이 영향을 주는것은 데이터이다. 
정제된 데이터 + 많은 데이터 건수 -&gt; 좋은성능 </li>
<li>모델구조 : 모델이 복잡해질수록 성능이 좋아진다 -&gt; 어디까지 복잡해야하는지 기준을 잡기위해 복잡한 모델을 만들고 거기에 규제를 두어서 과적합 문제해결 </li>
</ul>
<blockquote>
<p>** 🚨 최근 딥러닝 모델링 추세</p>
</blockquote>
<ol>
<li>가능한 한 복잡한 구조의 모델을 만듦</li>
<li>규제기법으로 과적합방지 **</li>
</ol>
<h3 id="📌-functional-api">📌 Functional API</h3>
<ul>
<li>** Sequential 모델 : 하나하나 layer 쌓아가는 모델 생성**</li>
<li>** Functional 모델 : 모델을 좀더 복잡 , 다중입력 • 다중출력 가능 **</li>
</ul>
<blockquote>
<ul>
<li>** Functional 실습  **
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/4ba75384-efe4-4eb4-abb9-39833cde90ef/image.png" /></li>
</ul>
</blockquote>
<ul>
<li>위 코드에 dropout 추가한실습캡쳐추가 </li>
</ul>
<h3 id="📌-다중모델-ㅣ-다중입력">📌 다중모델 ㅣ 다중입력</h3>
<blockquote>
<ul>
<li><strong>데이터구조</strong>
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/dbe0b46e-52e7-451b-8ba3-970eabaa3ed0/image.png" /> <br /></li>
</ul>
</blockquote>
<ul>
<li><strong>다중입력 실습</strong>
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/0638d38e-d9be-49ae-8c6d-8fb6b41ca8a2/image.png" /></li>
</ul>
<h3 id="📌-시계열-모델링">📌 시계열 모델링</h3>
<h4 id="✅-시계열데이터sequential-data-의미">✅ 시계열데이터(Sequential Data) 의미</h4>
<ul>
<li>시간의흐름에따른 순서가있는 데이터 = 패턴이 존재한다 = 이전data가있어서 지금data가 있을 수 있다. 
ex) 음성데이터, 문자데이터, 주가데이터 </li>
</ul>
<h4 id="🚨-음성데이터가-시계열데이터-">🚨 음성데이터가 시계열데이터 ? <img alt="" src="https://velog.velcdn.com/images/victoryone/post/8dd1f420-987d-43af-b284-e74443b55f44/image.png" /></h4>
<h4 id="✅-시계열데이터-모델링-종류">✅ 시계열데이터 모델링 종류</h4>
<p>1) 통계적 시계열 모델링
2) ML(머신러닝)기반 시계열 모델링 </p>
<ul>
<li>x1,x2,x3 -&gt; 도메인을 이해하고 feature을 만들어야한다. 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/d89b274c-da01-41a6-b70c-4cf9fe557fe8/image.png" /></li>
</ul>
<p>3) DL(딥러닝)기반 시계열 모델링 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/1438ec86-e3e7-4351-8935-c48e4d7cb1bd/image.png" /></p>
<ul>
<li>수업에선 DL(딥러닝)기반 시계열 모델링위주로 배웠다.</li>
</ul>
<h4 id="✅-시계열-모델링-절차">✅ 시계열 모델링 절차</h4>
<ul>
<li>시리얼데이터에선 train_err를 분석한다.
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/07ec0e29-4266-47fb-a373-bf6871e39e73/image.png" /></li>
<li>시계열 모델 평가
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/75669b9c-4532-4c09-a1a4-9457718e3aa1/image.png" /></li>
</ul>
<h3 id="📌-rnn-모델--재귀신경망모델">📌 RNN 모델 : 재귀신경망모델</h3>
<blockquote>
<ul>
<li>** RNN 모델 실습 ** </li>
</ul>
</blockquote>
<p>시계열 데이터에서 시간의 흐름과 각 시점의 특성을 함께 학습할 수 있도록 하기 위해 RNN 입력의 3차원 형태를 가진다.</p>
<pre><code>입력 데이터 차원=(samples,timesteps,features)</code></pre><ul>
<li><p>3차원구조 만들기 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/8dcc26f9-5883-449f-a42a-e801909885b8/image.png" /><img alt="" src="https://velog.velcdn.com/images/victoryone/post/3f099ece-bd46-47ec-b4d0-512c19f305fc/image.png" /></p>
</li>
<li><p>학습,평가데이터 나누기 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/704d3ca2-61ff-4c3a-815e-182486b91058/image.png" /></p>
</li>
<li><p>RNN 모델 설계 <img alt="" src="https://velog.velcdn.com/images/victoryone/post/c355e7e3-8f9a-4b20-b34a-05e8a9721e75/image.png" /></p>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/5802f5e0-5b29-47d0-acea-4153630ecd03/image.png" /></p>
<ul>
<li>Dense Layer는 입력 데이터를 1차원 벡터로 변환해야 하므로, 입력 데이터의 형상이 (batch_size, height, width)인 경우에는 먼저 Flatten해야 합니다. 즉, return_sequences=True 인경우 Flatten 필수 </li>
</ul>
<h3 id="📌-lstm-모델">📌 LSTM 모델</h3>
<ul>
<li>RNN모델의 문제인 장기의존성(예전데이터 기록이 흐려지고 최근데이터의 비중이 높아지는 문제)문제를 개선한 모델 </li>
</ul>
<h3 id="📌-lstm-모델실습---따릉이-🚲--2시간후-대여량예측하기">📌 LSTM 모델실습 - 따릉이 🚲 : 2시간후 대여량예측하기</h3>
<ul>
<li><p>y값이 클때 스케일링하기 ! 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/f137cc50-a8e1-4833-bfc7-ed89b9a461cd/image.png" /> </p>
</li>
<li><p>대신 예측할때 다시 원래 사이즈로 되돌려야한다.
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/f968514d-33dc-4b57-812d-c30e4052e0b2/image.png" /></p>
</li>
<li><p>LSTM 모델 </p>
</li>
<li><p>return_resquences = True 일때는 모든데이터를 다음레이어에 입력데이터로 전달한다. 만약 False이면 마지막값만 전달된다. 그래서 다음에 LSTM이면 True로 설정해야한다. False로 되어있으면 오류난다.</p>
</li>
<li><p>LSTM(2차원) -&gt; Dense(1차원) 이므로 차원을 변경하기위해 Flatten() : 행(분석단위)기준으로 옆으로 붙여 1차원으로 만들어준다.  </p>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/636140d5-b769-448a-b65a-fa03f50a0000/image.png" /></p>
<ul>
<li>va_err 그래프가 들쑥날쑥한 이유 : val_data(평가데이터) 가 많지않을때 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/b6b2cbb0-28ff-4a23-a6cd-1f67572f6787/image.png" /></li>
</ul>
<blockquote>
<p>** 딥러닝까지 배우면서 강사님은 기술적인 능력도 중요하지만 못지않게 비즈니스문제해결능력도 굉장히 중요하다고 하셨다. 그러므로 나는 ai 로 비즈니스문제를 해결하는 해결사가 되자 ! 라고 생각하라고 하셨다. **</p>
</blockquote>