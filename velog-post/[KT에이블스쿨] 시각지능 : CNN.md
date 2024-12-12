<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/7daa6cd9-f807-4e36-b46b-e34f3beb4204/image.gif" /></p>
<p>** 🍀10/21 - 10/25**</p>
<hr />
<br />

<h2 id="📌-시각지능">📌 시각지능</h2>
<h3 id="📖-컴퓨터-비전computer-vision">📖 컴퓨터 비전(Computer Vision)</h3>
<p>컴퓨터가 이미지나 동영상을 이해하고 해석할 수 있도록 하는 기술분야이다. 
인간이 시각적으로 인식하는 능력을 컴퓨터에 적용하는 것이 목표이다. 
컴퓨터 비전은 머신러닝과 딥러닝을 활용하여 패턴을 인식하고 이미지를 분석하는 데 사용된다. </p>
<ul>
<li><a href="http://cocodataset.org/#explore">COCO Explorer: Show Captions</a> : 컴퓨터 비전 작업을 위한 데이터셋 링크 </li>
</ul>
<br />

<hr />
<br />

<h4 id="mission-컴퓨터가-이미지를-이해하게-하는-것">Mission “컴퓨터가 이미지를 이해하게 하는 것”</h4>
<p><em><strong>Visual Processing Mechanism</strong></em> : 컴퓨터 비전에서 인간의 시각 처리 매커니즘을 유사한 과정을 모방하여 이미지와 비디오에서 정보를 추출하고 이해하려고 한다.</p>
<p>그런데 컴퓨터가 이미지를 파악하는데 어렵다 .. 
왜냐하면 컴퓨터는 0,1로 명령어를 받고 , 화면은 pixel (picture element 화면을 구성하는 가장 기본이 되는 단위) 로 구성되어 있기때문이다. </p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/c1d146a6-49e9-4660-bb01-c8a6c27e6a2b/image.png" /></p>
<ul>
<li>일부분만 보았는데도 복잡하고 픽셀만 본다면 무엇인지 알 수 없다.</li>
</ul>
<p>✍🏻 컴퓨터에게 경계(외곽선:Edge Detection)를 가르쳐 보자 !
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/44544a0f-30f3-4a4c-8c03-3613cfb6ab68/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/5cdd819c-4704-4891-a90f-43969d5f68ed/image.png" /></p>
<p>하지만 .. Edge Detection 조차 쉽지 않다 .. ! </p>
<p>✍🏻 그럼 고양이픽셀을 학습시키면 되지 않을까 ? 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/a3899095-065b-4569-9335-1c52986e2c33/image.png" />
하지만 .. 
같은 고양이라도 카메라 각도 , 명암 , 움직임에 따라 이미지(데이터)가 바뀌게 된다.</p>
<br />

<hr />
<br />

<p><strong>문제는 알고리즘이 아니라 데이터 - 페이페이 리</strong></p>
<ol>
<li>데이터의 양이 많아야 한다.</li>
<li>데이터의 레이블이 잘 되어있어야 한다.</li>
</ol>
<ul>
<li>ImageNet : 컴퓨터 비전과 딥러닝 분야에서 가장 유명한 대규모 이미지 데이터셋 중 하나이다.<br />약 1,000개의 물체 카테고리를 포함하고 있으며, 데이터셋 전체로는 1,400만 개 이상의 이미지가 포함되어 있다.<ul>
<li>ILSVRC(이미지넷 대규모 시각 인식 챌린지): ImageNet은 매년 <strong>ILSVRC(ImageNet Large Scale Visual Recognition Challenge)</strong>라는 대회를 개최하여, 객체 인식과 분류 작업에서 어떤 모델이 가장 높은 성능을 발휘하는지 경쟁했고 이 대회는 딥러닝 모델, 특히 <strong>Convolutional Neural Networks(CNN)</strong>의 발전에 큰 기여를 했다.</li>
</ul>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/47b09eb9-6c9e-4e81-844b-08688fc06385/image.png" /></p>
<ul>
<li>CNN알고리즘을 적용하고 나서 오류율이 많이 낮아졌고 결국 인간의 오류율보다 낮아졌다. </li>
</ul>
<br />

<h2 id="📌-convolutional-neural-network-cnn">📌 Convolutional Neural Network (CNN)</h2>
<ul>
<li><h4 id="fully---connected-구조"><strong>Fully - Connected 구조</strong></h4>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/a7094bbc-01c9-4c25-b30f-711fb31b28dd/image.png" /></p>
</li>
<li><p>위 1 , 3 =  색상 채널  수 , 깊이 </p>
</li>
<li><p><em>Deep Neural Network (DNN) *</em> 가 가진 구조는 <strong>Fully - Connected 구조</strong> 이다.</p>
</li>
<li><p><em>Fully - Connected 구조 : 인풋 - 히든레이어(keras 의 dense 함수만 사용하는 구조 ) - 아웃풋*</em>
: 모든 노드(뉴런)가 하나하나 전부연결 (빽빽하게 연결되어있음) = 전결합 , 완전결합     </p>
</li>
<li><p>Fully Connected Layer (전결합층) 은 모든노드가 빽빽하게 연결되어있는 구조를 가진다. </p>
</li>
</ul>
<p>하지만 Fully Connected 구조는 일정 정도 성능나오는데 , 컬러이미지 분류하는 문제에서 한계가 발생한다.
MNIST <a href="https://www.tensorflow.org/datasets/catalog/mnist?hl=ko">MNIST 데이터셋링크</a>  : 일정 정도 성능 나옴 (흑백이미지)
그렇지만 CIFAR <a href="https://www.cs.toronto.edu/~kriz/cifar.html">CIFAR 데이터셋링크</a> 또는 현실문제에서는 성능이 떨어진다 
➡️ 이미지데이터 구조를 파괴하여서 접근하는 것이 과연 올바른가 ?
➡️ 아예 이미지데이터에 접근방식을 새롭게 하자
따라서 이미지데이터의 형식을 훼손하지않고서 특징들을 추출하는 다른방식의 알고리즘 등장
--&gt; 이 알고리즘을 *<em>Convolutional Neural Network *</em>라고 한다. </p>
<br />

<hr />
<br />

<ul>
<li><h4 id="convolutional-neural-network-구조">Convolutional Neural Network 구조</h4>
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/e95141eb-b295-4e46-b2a6-885317ee9135/image.png" /></li>
<li>convolutional layer인 filter 는 ** 예시에선 1,0 으로만 표현됐지만 다양한 값이 들어갈 수 있다**. 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/f4dfffc5-293d-4712-a689-53bf43a620e8/image.gif" /></li>
<li>필터가 슬라이딩하여 만들어진 부분부분에서 고유한 특성을 가진 *<em>feature map *</em>
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/ce5deec8-acbd-40b3-a413-c2d676818284/image.png" /></li>
<li>feature map 
= 서로 다른 값들을 가지고 있는 feature 
= ConV Layer 를 거쳐져 만들어진 서로 다른 feature </li>
</ul>
<p>픽셀 x Filter = feature , 이러한 feature가 모여 feature map을 형성한다.</p>
<p>입력 이미지 크기: 32 x 32 x 3 ( * 3 =&gt; 깊이, 채널 ,색상(단색) )
필터 크기: 5 x 5 x 3 (가로 5, 세로 5, 깊이 3)</p>
<ul>
<li><p>Filter - 가중치는 다양한 값을 가질 수 있다</p>
</li>
<li><p>feature size 설정할 수 있다. </p>
</li>
<li><p>input의 depth를 filter의 depth가 따라간다.
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/69880a45-332d-409c-8a73-b33d9ec1f200/image.png" /></p>
</li>
<li><p>Stride : Filter의 이동 보폭 </p>
</li>
<li><p>Stride = 1
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/228412a5-27f9-4ae7-94c2-ddc996b29cea/image.png" /></p>
</li>
<li><p>3 x 3 feature map 을 만들어짐  </p>
</li>
<li><p>Stride = 2 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/b07646a2-ee35-44c4-9101-72f3507e1afd/image.png" /></p>
</li>
</ul>
<ul>
<li><p>보폭이 feature mpa 크기 ( 즉, 가로세로 크기) 에 영향을 준다. </p>
</li>
<li><p>stride를 정하는 기준 : 얼마나 세밀하게 정할것인지 기준을 세워놓고 정한다.</p>
</li>
<li><p>stride 보폭으로 인해 특정 위치의 픽셀 값을 고려하지 않아 필터가 놓쳐 Stride =1 보다 더 정보손실이 생길 수 있다. 하지만 이게 학습성능이 떨어지는지는 모른다 =&gt; 학습을 시켜서 알아봐야한다.
겹치는 부분이 생겨서 성능이 더 떨어질 수 도 있기때문에</p>
</li>
<li><p>Padding : 채워넣다.
딥러닝에서 패딩은 이미지나 입력 데이터의 가장자리를 특정 값으로 채워 넣는 것을 의미</p>
</li>
<li><p>패딩(Padding)**은 합성곱 신경망(CNN)에서 이미지의 가장자리 부분을 처리할 때 사용되는 기술입니다. 합성곱 연산을 수행할 때, 필터가 이미지의 가장자리에 도달하면 전체 이미지 정보를 다룰 수 없기 때문에 이 문제를 해결하기 위해 패딩이 사용된다. </p>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/dfd534d7-df3a-4f5e-8993-262e7bca361a/image.png" /></p>
<ul>
<li>기본적으로 0울 추가 </li>
</ul>
<h3 id="📖-padding-하는-이유-">📖 *<em>padding 하는 이유 *</em></h3>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/4efcaa30-1dc4-4d86-8c2a-b28273d24e74/image.png" /></p>
<ul>
<li>동그라미 부분이 padding이 없다면 한 번 만 거친다. 그런데 만약 padding을 추가하면 4번으로 늘어난다. </li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/0371a7e5-f6a6-4264-bbf2-08008f6345f7/image.png" /></p>
<ul>
<li>32 x 32 : 0 ~ 31 칸 존재 </li>
<li>유효한 위치 : 32−5=27칸까지 표현가능 , 28칸 부터 표현불가능</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/2708b92f-6fee-4160-ac1d-6849af7b6e23/image.png" /></p>
<ul>
<li>같은 숫자 64지만 , 가지고 있는 의미는 다르다.</li>
<li>앞 64보다 뒤 64가 <strong>더 복잡한 , 고급 level이다.</strong></li>
</ul>
<p>floor라서 floor(1.5) + 1 = 1 +1 = 2입니다</p>
<p>filter = 32 : 서로 다른 가중치를 사진 필터의수 
커널 사이즈 = filter의 가로세로 사이즈
strides = 이동보폭 , 기본값은 (1,1)
padding = 기본값 'vaild' : 패딩사용하지않음 , 'same' : 패딩사용</p>
<h3 id="📖-pooling-layer">📖 Pooling Layer</h3>
<ul>
<li><strong>Pooling Layer 사용이유</strong> :  연산량을 줄이려는 이유가 제일 크다 </li>
</ul>
<h3 id="📖-maxpooling-layer">📖 MaxPooling Layer</h3>
<ul>
<li>MaxPooling은 필터 영역에서 가장 큰 값을 선택하고 , 이미지에서 가장 두드러진 특징을 유지하는 데 적합하다. </li>
<li>MaxPooling + 'Relu'(음수값을 0으로 처리) &gt;&gt;&gt; 시너지효과가 난다</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/fd3bb1f0-1ce3-4d1c-a59e-52b7c7a21ac5/image.png" /></p>
<ul>
<li>VGG 2014 2nd </li>
</ul>
<p>![]
(<a href="https://velog.velcdn.com/images/victoryone/post/e063c1be-ff1e-4bb6-8371-974025d98c14/image.png">https://velog.velcdn.com/images/victoryone/post/e063c1be-ff1e-4bb6-8371-974025d98c14/image.png</a>)</p>
<ul>
<li>max-pooling (2,2) 를 하면 feature size 가 반으로 준다 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/6b3c1b7e-5d23-46e3-b7bb-6d9bb9153b7e/image.png" /></li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/8b09635f-c328-49c8-ae08-fe5ab61be4cf/image.png" /></p>
<h3 id="📖-averagepooling">📖 AveragePooling</h3>
<p>, AveragePooling은 필터 영역의 평균 값을 사용
, AveragePooling은 전반적인 특징을 더 부드럽게 요약하는 데 사용된다.</p>
<ul>
<li>LeNet-5 + Avg-pooling  (pooling filter size, stride)</li>
<li><em>Average Pooling (Avg Pooling)*</em>은 합성곱 신경망(CNN)에서 자주 사용되는 다운샘플링 기법입니다. 이 기법은 특징 맵의 크기를 줄이는 동시에 중요한 정보를 유지하는 데 도움이 됩니다. Avg Pooling의 주요 개념과 작동 방식을 설명해드릴게요.</li>
</ul>
<h3 id="🏷️-정리-및-요약">🏷️ 정리 및 요약</h3>
<p>딥러닝 </p>
<ul>
<li>layer가 깊어질수록 high-level feature 를 extract 하더라 </li>
</ul>
<p>CNN </p>
<ul>
<li><p>Conv Layer : filters / kernel_size : 이전 depth을 따라간다 / strides : 보폭 / padding : 패딩 , 기본적으로 zero padding 을 사용 -&gt; featrue 사이즈 줄어드는것을 방지 + 가장자리 데이터 손실방지 / Activation fuction </p>
</li>
<li><p>Pool Layer : pool_size  /  strides -&gt; strides사이즈는 기본적으로 pool_size 를 따라간다. </p>
</li>
</ul>
<h3 id="🗂️-추가공부--질문--서치-">🗂️ 추가공부 ( 질문 &amp; 서치 )</h3>
<h4 id="1-keras에서는-fully-connected-layer--cnn-등-여러구조가-있는데-그렇다면-scikit-learn은-무슨-구조일까-">1. keras에서는 Fully Connected Layer , CNN 등 여러구조가 있는데 그렇다면 Scikit-learn은 무슨 구조일까 ?</h4>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/6591b27f-feb1-41de-8099-103cd4fa165d/image.png" />  </p>
<ul>
<li>사이킷런은 딥러닝 모델구조가 아닌 머신러닝 알고리즘 구조이다.
따라서 히든레이어를 쌓는 방식이 아니고 단일 알고리즘을 통해 결과를 예측한다. </li>
</ul>
<h4 id="2-keras-스케일링">2. keras 스케일링</h4>
<p>sklearn의 minmaxscaler는 이미지 데이터보다는 태블로(tableau)데이터에 적합하다. 
따라서 이미지데이터에 사용하게되면 에러발생 가능성이 높으므로 Min-Max 정규화를 혹은 Standardization 표준화를 사용한다. </p>
<ul>
<li>Min-Max 스케일링 수식 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/65a24873-524b-4ddb-b8f3-0ff53a3edb3c/image.png" /></li>
<li>따라서 이미지는 0~255값을 가지므로 정규화를 255.0으로 나누어 사용한다. </li>
<li><em>x = x / 255.0   *</em></li>
</ul>
<h4 id="2-1-스케일링을-하는이유">2-1. 스케일링을 하는이유</h4>
<ul>
<li>학습수렴속도 줄이고 , 값의 통일성 </li>
<li>activaion fuction 중 sigmoid function을 쓸때 기울기 소실 문제 ( -&gt; 가중치업데이트가 안된다) 를 줄여준다.</li>
</ul>
<h4 id="3-keras-인코딩">3. keras 인코딩</h4>
<ul>
<li>One-hot encoding , Labelencoding , get_dummies 를 사용해도된다. 
강사님은 to_categorical 함수를 추천하셨다. 
to_categorical - 주로 다중 클래스 분류 문제에서 정수 레이블을 쉽게 원-핫 인코딩으로 변환</li>
</ul>
<h4 id="4-test_y-에도-one-hot-encoding-하는이유">4. test_y 에도 One-hot encoding 하는이유</h4>
<ul>
<li><p>y값 원핫 인코딩을 하면 데이터가 크고 다중분류 클래스가 많을 때 다루기 좋고 , shape 찍을 때 해당 데이터 분류 클래스 수가 직관적으로 보인다.</p>
</li>
<li><p>y값이 0<del>9 가 아니라 a</del>j 일 경우엔 필수</p>
</li>
</ul>
<h4 id="5-batchnormalization-이란-">5. BatchNormalization() 이란 ?</h4>
<ul>
<li><p>직관적인 의미 : 히든레이어를 한 번 더 스케일링 하는 것 </p>
</li>
<li><p>Batch Gradient Descent _  OOM (out of memory) 이슈 
OOM (Out of Memory)**는 말 그대로 &quot;메모리 부족&quot; 상태를 의미한다. 컴퓨터 시스템이 처리해야 할 데이터의 양이 할당된 메모리 용량을 초과하여 발생하는 오류</p>
<ul>
<li>Batch Gradient Descent +  Stochastic Gradient Descent (SGD) = Mini Batch Gradient Descent</li>
<li>BatchNormalization()에서 사용되는 '배치'는 <strong>미니 배치(mini-batch)</strong>를 의미 
![]
(<a href="https://velog.velcdn.com/images/victoryone/post/9022de4c-9260-403e-a44d-3ec3a1e24a2a/image.png">https://velog.velcdn.com/images/victoryone/post/9022de4c-9260-403e-a44d-3ec3a1e24a2a/image.png</a>)</li>
<li>디폴트 batch_size 는 32 , <strong>batch_size =32를 Mini Batch Gradient Descent</strong> 라고 한다.</li>
</ul>
</li>
<li><blockquote>
<p><strong>32</strong> [batch_size] <strong>x 1500</strong> =** 60000** [전체 이미지개수]  <strong>x  0.8</strong> [전체데이터 中 학습데이터 비율] </p>
</blockquote>
</li>
<li><h4 id="mini-batch-gradient-descent는-두-방법의-중간-지점으로-데이터를-작은-배치로-나누어-처리하여-균형을-이룬다">Mini-Batch Gradient Descent는 두 방법의 중간 지점으로, 데이터를 작은 배치로 나누어 처리하여 균형을 이룬다.</h4>
<ul>
<li>Batch Gradient Descent는 전체 데이터를 한 번에 처리합니다.
Stochastic Gradient Descent는 각 데이터 포인트를 개별적으로 처리합니다.</li>
</ul>
</li>
<li><h4 id="6-batchnormalization-위치">6. BatchNormalization() 위치</h4>
</li>
<li><p>전처리단계에서 스케일링을 하기때문에<br />1) Input - BatchNormalization - Conv 이 순서로 실행하다가</p>
</li>
<li><p><em>2) Input - Conv - BatchNormalization*</em> 로 놓았을때 성능이 더 좋아서 지금은 2) 순서로 사용하고 있다.  </p>
</li>
</ul>
<h3 id="qa">[Q&amp;A]</h3>
<p><em>*<em>보통 Zero Padding으로 많이 하는데 배경이 1위주인경우. 1로 하는게 더 유리해 보이는 경우에도 0으로 하는 이유는 ? *</em></em></p>
<ul>
<li>1로 줄 수 있기하지만 , Zero Padding 관습적인것이다.</li>
</ul>