<h3 id="📌-앙상블-ensemble">📌 앙상블 (Ensemble)</h3>
<ul>
<li>약한모델들을 합쳐서 더 정확하고 견고한 모델을 만드는 방법</li>
<li>앙상블 종류 1)보팅 2)배깅 3)부스팅 4) 스태킹</li>
</ul>
<h3 id="1-보팅-voting">1) 보팅 (Voting)</h3>
<ul>
<li>예측결과를 투표를 통해 최종예측결과 결정하는 방법</li>
</ul>
<h3 id="2-배깅-bagging-🌟">2) 배깅 (Bagging) 🌟</h3>
<ul>
<li>데이터를 부트스트랩 (원본 데이터에서 반복적으로 샘플을 무작위로 추출하여 통계적 추정치를 계산하는 방법) 한 데이터를 학습시킨 후 , 예측결과를 집계해 최종결과를 얻는방법</li>
</ul>
<img alt="Example" height="300px" src="https://velog.velcdn.com/images/victoryone/post/f8df70a5-6492-46fd-8b0d-395c2ddba56b/image.jpg" width="400px" />

<ul>
<li>이때 같은유형의 알고리즘을 사용하고 , 부트스트랩시 중복허용한다.</li>
<li>범주데이터는 : 보팅 , 연속형데이터는 : 평균 으로 결과 집계</li>
<li>대표적인 배깅 알고리즘 -&gt; RandomForest (Decision Tree만사용)</li>
</ul>
<h4 id="randomforest">RandomForest</h4>
<ul>
<li>1) 랜덤하게 데이터 샘플링 2) 개별모델트리 구성시 분할기준되는 Feature 랜덤선정</li>
<li>여러 Decision Tree가 모여 Forest가 됨</li>
<li>max_depth (트리의 최대깊이) / n_estimators (Decision Tree 개수) 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/76c90ad6-ca3a-45dd-850f-82de0223646e/image.png" /></li>
</ul>
<h3 id="3-부스팅-boosting">3) 부스팅 (Boosting)</h3>
<ul>
<li>같은유형 알고리즘 기반모델 여러개 순차적학습</li>
<li>이전모델에서 예측못한 데이터에 가중치 부여해 다시 예측 </li>
<li>예측성능 뛰어나 배깅보다 성능이 좋지만 속도가 느리고, 과적합 발생 가능성 있다.</li>
<li>대표적 부스팅 알고리즘 : XGBoost , LightGBM </li>
</ul>
<img alt="Example" height="300px" src="https://velog.velcdn.com/images/victoryone/post/a1c218ed-84ca-4f46-8c33-31cb064554eb/image.jpg" width="400px" />

<h3 id="4-스태킹-stacking">4) 스태킹 (Stacking)</h3>
<ul>
<li>여러모델 예측값을 최종 모델의 학습데이터 사용하여 예측하는 방법
EX) KNN , XGboost , Logistic Regression 모델을 사용해 4가지 예측값 구한후 
Random Forest 학습데이터로 사용 </li>
</ul>