<blockquote>
<p>이번주 내내 언어지능을 공부하고 있어요 (●'◡'●) 수업내용도 재밌는데 , 요새 기술현황얘기도 많이 해주셔서 재밌게 들었습니다. 파이썬도, 코드도 처음보다 실력이 늘어서 수업도 이해가 잘 되고 수학적내용이 많다보니 더 재밌게 들을 수 있었던 언어지능강의 였습니다 💚 </p>
</blockquote>
<br />


<h2 id="💻-실습-dl_binary_nn">💻 실습 DL_Binary_nn</h2>
<hr />
<ul>
<li>Pytorch 구현 &amp; 히든레이어 3개 
<a href="https://github.com/wsw579/TIL/blob/main/20241107">Github DL_Binary_nn</a></li>
</ul>
<br />

<h2 id="📌-gan">📌 GAN</h2>
<hr />
<ul>
<li>GAN (쉬운데널리쓰이는모델) , Generative Adversarial Network
두 개의 신경망이 서로 경쟁하면서 더 나은 결과를 만들어내는 구조이다.
GAN은 이름 그대로 두 네트워크가 서로 &quot;적대적(adversarial)&quot;으로 학습을 진행한다.</li>
</ul>
<p><strong>[생성자(Generator)]</strong></p>
<ul>
<li>가짜 이미지를 생성하는 신경망이다.
무작위 노이즈(z)를 입력으로 받아 진짜처럼 보이는 데이터를 생성
예를 들어, z를 입력받아 가짜 이미지를 만들어 내
생성자는 판별자가 더 이상 진짜와 가짜를 구분하지 못하게 하는 것이 목표이다.</li>
</ul>
<p><strong>[판별자(Discriminator)]</strong></p>
<ul>
<li>입력받은 데이터가 진짜 데이터인지 가짜 데이터인지 판단하는 신경망이다.
진짜 데이터(실제 데이터셋의 샘플)와 생성자가 만들어낸 가짜 데이터를 구분한다.
판별자는 생성자가 만든 가짜 데이터를 최대한 잘 구분해내는 것이 목표이다.</li>
</ul>
<hr />
<h4 id="💻-mnist--gan">💻 MNIST + GAN</h4>
<blockquote>
<p>인풋 :: 노이즈 
생성자 (도둑) 
H1 : Noise 사이즈 x 유닛수  ---------&gt; Noise 데이터는 몰라도  Noise 사이즈는 알고있어야한다. 
OUT : 유닛수 * MNIST 숫자에 필요한 디멘션 
아웃풋 :: MNIST ( 숫자생성)   =  28 X 28</p>
</blockquote>
<blockquote>
<p>인풋 :: MNIST 이미지 (구별해야하니까 진짜이미지를 알아야한다) 
구별자 (경찰)<br />H1 : MNIST 숫자에 필요한 디멘션  * 히든레이어에 맞는 디맨션
OUT :  히든레이어에 맞는 디맨션 * 1 (0또는 1)
아웃풋 :: 0,1 (진짜인지 가짜인지 구별 ; 1에 가까이 갈 수록 닮음) </p>
</blockquote>
<p>*<em>COST 함수 *</em>  분류가 잘 되게하기위한 목적 ( OR 실제값과 최대한 가깝게 만들기 위해 사용한다)
어떤 목적을 위해 설계된 것, GAN에서 COST함수를 어떻게 만드는지가 중요하다.</p>
<p>*<em>1. 판별자(Discriminator) COST함수 *</em>
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/30ac7112-af66-4b2f-a736-2356feffe442/image.png" /></p>
<ul>
<li>첫 번째 항: 진짜 데이터에 대해 D(x)가 진짜일 확률을 최대화
두 번째 항: 생성된 가짜 데이터에 대해 D(G(z))가 가짜일 확률을 최소화</li>
</ul>
<p>** 2. 생성자(Generator) COST함수 **
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/90fc0c3f-df51-4c11-b2a1-260c80fc9638/image.png" /></p>
<ul>
<li>D(G(z))가 1에 가까워지도록 학습. 즉, 가짜 데이터가 진짜로 분류되도록한다.</li>
</ul>
<p>그런데 이때 이슈가 있다. 
💡<strong>하나의 코드에 두 개의 모델(두개의 신경망)을 만들면 (제너레이터 , 디스크리미너레이터) 파라미터가 섞일 수 있다.</strong></p>
<blockquote>
<p>즉, 위조지폐를 대충만들어도 구별자들을 바보로 만들면 (=파라미터를 건들면) 위조하기 쉬워지고
또는 구별자들의 성능이 높지않은데 위조지폐 성능을 나쁘게 만들면 구별자가 구별할 수 있는 성능이 높아진다.</p>
</blockquote>
<p>결론적으로 optimizer 를 두 개로 만들어서 파라미터를 개별적으로 넣어줘야한다.</p>
<blockquote>
<p>생성자 optimizer ( 생성자 파라미터 )
구별자 optimizer ( 구별자 파라미터 )
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/644bb75e-3b77-48db-878e-dc9ef2a88f48/image.png" /></p>
</blockquote>
<br />

<h2 id="📌-차원축소">📌 차원축소</h2>
<hr />
<p><strong>1) LDA</strong> : 어떤모양이든 상관없으니까** 분류만 잘 되게 축소한다.**
*<em>2) PCA *</em> :  데이터가 가장 넓게 퍼진 방향을 기준으로 주요 축을 설정하며, 데이터내용을 고려하지않고 차원축소 </p>
<blockquote>
<p>*<em>PCA 추가공부  *</em></p>
</blockquote>
<ul>
<li>데이터가 많이 분산되어 있다는 것은 데이터가 여러 방향으로 퍼져 있고, <strong>변화가 크다는 뜻</strong>입니다.
이 변화가 크다는 것은 <strong>많은 정보가 포함되어 있다</strong>는 의미입니다. 즉, *<em>데이터가 다양한 특성을 *</em>가지고 있어서, 그것을 분석하면 더 많은 정보를 얻을 수 있습니다.
그래서 PCA는 분산이 큰 방향을 찾아서 데이터를 그 방향으로 축소하게 되면, 중요한 정보를 유지하면서 차원을 줄일 수 있게 됩니다.</li>
</ul>
<br />

<h2 id="📌-overfitting">📌 Overfitting</h2>
<hr />
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/6fe41471-4986-4b92-b6de-4104f3d525ea/image.png" /></p>
<ul>
<li><p>위 그래프가 오버피팅인가 ? 🅰️ 아직 알 수 없다.</p>
<ul>
<li>a ( 검은선 )  /  b ( 녹색선 )<br />a 처럼 학습 후 b 처럼 추론이 되면 b처럼 학습해야하는것이고 
b 처럼 학습 후 a 처럼 추론이 되면 a처럼 학습해야하는 것이다.
즉 , 이 상황에서 a,b 둘 중에 뭐가 맞는 지 모른다.
그래서 ** 오버피팅은 학습 후 결과로 판단해야한다**. </li>
</ul>
</li>
<li><p>*<em>오버피팅 판단 *</em>:  b라고 판단하고 학습했지만 결과가 a로 나오면 그때서야 판단함</p>
<blockquote>
<ul>
<li><strong>오버피팅 해결책</strong> : 데이터가 많이 제공되면 해결할 수 있는데 대부분 데이터가 많이 제공되지 않는다. 
feature 개수를 줄여서 성능이 줄더라도 일반화시키기 <br /> *<em>why ? *</em> 특징을 줄이는 이유는, 너무 많은 특징을 사용할 경우 모델이 훈련 데이터의 세부적인 패턴에 과도하게 적합되기 때문이다. <br /></li>
</ul>
</blockquote>
</li>
<li><p><em>Autoencoding*</em>  <br /> 중요한 feature만 남기고 차원축소 -&gt; 학습 -&gt; 다시 디코더  <br />PCA (= 차원축소) 에서 발전되어 Autoencoding 만들었다.</p>
</li>
</ul>
<p>💡 RNN  ( Recurent Neural Networks ) : 현대 자연어처리와는 많이 관계가 없다. </p>
<br />

<h2 id="📌-rl-강화학습">📌 RL 강화학습</h2>
<hr />
<ul>
<li>강화학습은 주어진 환경에서 <strong>최적의 행동 시퀀스를 찾아</strong>, 예상되는 <strong>보상을 최대화</strong>한다. 
행동과 보상을 정의하고, 최적의 행동을 취하는 과정에서 보상을 최대로 받을 수 있는 방법을 학습하는 것이다.</li>
</ul>
<p>💡 *<em>강화학습 수학적으로도(MDP) , 성능도 최적(optimal)으로 잘 분류하는데 왜 딥러닝을 사용하나 ? *</em></p>
<ul>
<li><p>강화학습은 학습 과정이 복잡하고 계산 비용이 많이 들며, 특히 환경이 복잡할수록 훈련 시간이 오래 걸릴 수 있다. 즉, 상태과정에서 벗어나지 못하고 결과가 나오지 않을 수 있다.</p>
</li>
<li><p>또한 <strong>현재 강화학습과 예전 강화학습의 의미가 달라졌다.</strong>
현대 강화학습은 지도학습이다. state , action 을 신경망으로 맵핑시키기 때문이다.
신경망을 사용해 학습과정은 빨라졌지만 , 최적의 결과를 보장하지못한다.</p>
</li>
</ul>
<h4 id="inverse-reinforcement-learnign-irl--역-강화학습">Inverse Reinforcement Learnign (IRL) : 역 강화학습</h4>
<p>강화학습 中 앤드류 응 | Inverse Reinforcement Learnign (IRL)</p>
<blockquote>
<p>전 행동을 보고 거꾸로 돌아가서 리워드 찾기 : 인간이나 전문가의 행동을 관찰하여, 그들이 어떤 보상 함수를 최대화하려고 했는지 알아내는 것. 즉, 의도나 동기를 역으로 추정해내는 것이다.</p>
</blockquote>
<h4 id="lmitation-learning-ir--모방학습">lmitation Learning (IR) : 모방학습</h4>
<ul>
<li>리워드는 상관없이 강화학습 할 수 있다. </li>
<li>에이전트가 특정 작업을 수행할 때, 전문가나 인간의 행동을 모방하여 학습기법. 
보상 함수를 사전에 정의하지 않고, 대신 주어진 예시 행동을 보고 학습하므로 실제 환경에서 시도와 오류를 거치며 보상을 최대화하는 전통적 강화 학습 방식과 차별화된다.</li>
</ul>
<p>즉 , *<em>데이터를 많이 학습시키는 방식 *</em></p>
<ul>
<li>모든 데이터가 다른 행동을 한다면 (200명이 같은상황에서 다 다르게 행동한다면 ) 의미가 없다. 
lmitation Learning은 특정상황에서 어떤 한 사람의 행동을 학습시키는것이다. </li>
</ul>
<br />

<h2 id="📌-llm">📌 LLM</h2>
<hr />
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/192e662c-101d-419a-9d63-bd7cc3535a0b/image.png" /></p>
<ul>
<li>대표적인 예시 ** Chat gpt **<blockquote>
<p><strong>Chat gpt ** <br /> GPT (Generative Pretrained Transformer)- 3.5 기준으로 하고 있고 **인간 피드백을 바탕으로 한 강화 학습(RLHF)을 통해 추가적으로 미세 조정</strong>된다. <br /> 
GPT  : 
Generative (다음 단어를예측하는언어모델구축 ) 
Pre-trained (많은양의데이터를사전에훈련) 
Transformer (신경망에기반한 인코더-디코더)</p>
</blockquote>
</li>
</ul>
<br />

<h2 id="💻-실습-knn-구현">💻 실습 KNN 구현</h2>
<hr />
<ul>
<li>*<em>내가 구현한 knn *</em><pre><code># 내 코드 : 잘못된부분 - knn인데 k개 점이 속한 그룹 개수를 카운트한게 아니라 k번 반복하도록 구현됨 
</code></pre></li>
</ul>
<p>import numpy as np</p>
<p>group_A = np.zeros((15,2)) # 앞의 값은 샘플의 수 , 뒤의 값은 샘플의 dim
group_B = np.zeros((15,2)) # 모든 원소가 0인 , 2차원의 15행 2열
group_C = np.zeros((15,2))</p>
<h1 id="각-그룹마다-랜덤값을-부여함">각 그룹마다 랜덤값을 부여함</h1>
<h1 id="group-a는-100에서-200사이의-실수값">Group A는 100에서 200사이의 실수값</h1>
<h1 id="group-b는-0에서-50사이의-실수값">Group B는 0에서 50사이의 실수값</h1>
<h1 id="group-c는-x축은-100에서-200사이의-실수값--y축은-0에서-50사이의-실수값">Group C는 X축은 100에서 200사이의 실수값 , Y축은 0에서 50사이의 실수값</h1>
<p>np.random.seed(2024)  # 재현성을 위한 시드 설정
group_A = np.random.uniform(100, 200, (15, 2))
group_B = np.random.uniform(0, 50, (15, 2))
group_C[:,0]= np.random.uniform(100, 200, 15)
group_C[:,1] = np.random.uniform(0, 50 ,15)</p>
<h1 id="각-그룹의-점들과-우리가-가지고-있는-현재-point-와의-거리를-구하는-함수가-필요">각 그룹의 점들과 우리가 가지고 있는 현재 point 와의 거리를 구하는 함수가 필요</h1>
<p>def distance(p,a):
  return np.linalg.norm(p - a , axis=1)</p>
<p>k = 5</p>
<h1 id="각-그룹의-통계치를-나타내는-리스트">각 그룹의 통계치를 나타내는 리스트</h1>
<p>stat = [0,0,0]</p>
<p>point = np.random.uniform(-200,100,(2,))</p>
<p>for k in range(k):
  dist_A = distance(point, group_A)
  dist_B = distance(point, group_B)
  dist_C = distance(point, group_C)</p>
<h1 id="각-그룹이-가장-가까운-경우의-수-계산">각 그룹이 가장 가까운 경우의 수 계산</h1>
<p>  dist_A = np.min(distance(point, group_A))
  dist_B = np.min(distance(point, group_B))
  dist_C = np.min(distance(point, group_C))</p>
<p>  closest = np.argmin([dist_A, dist_B, dist_C])</p>
<h1 id="가장-가까운-그룹의-통계치-업데이트">가장 가까운 그룹의 통계치 업데이트</h1>
<p>  stat[closest] += 1</p>
<h1 id="제일-앞은-k개-중에-그룹-a에-해당하는-개수--그룹-b에-해당하는-개수--그룹-c에-해당하는-개수">제일 앞은 k개 중에 그룹 A에 해당하는 개수 , 그룹 B에 해당하는 개수 , 그룹 C에 해당하는 개수</h1>
<h1 id="가장-가까운-그룹-결정">가장 가까운 그룹 결정</h1>
<p>index = np.argmax(stat)</p>
<h1 id="이-stat에서-최대로-큰-값의-위치를-구하면-그게-그룹이-됨">이 stat에서 최대로 큰 값의 위치를 구하면 그게 그룹이 됨</h1>
<p>if index == 0:
  print(&quot;Group A&quot;)
elif index == 1:
  print(&quot;Group B&quot;)
else:
  print(&quot;Group C&quot;)</p>
<pre><code>&gt; ![](https://velog.velcdn.com/images/victoryone/post/c26780ae-f1cd-462c-9083-fde5ae10f9e0/image.png) &lt;br&gt;
- 실수한 점 : 모든 점들의 거리를 구하고 가장 가까운 순서대로 k번째까지 끊어야하는데 for문을 k번째 돌려버림 ; 



&gt; - ** KNN 구현 ** 
&gt;  
![](https://velog.velcdn.com/images/victoryone/post/b5ad34b3-3264-4570-a001-6dcdad319f21/image.png) &lt;br&gt;
- knn 핵심적인 부분: point와 그룹 별 모든 점들 사이 거리구하고 가장 근접한 k개까지 정렬 




</code></pre>