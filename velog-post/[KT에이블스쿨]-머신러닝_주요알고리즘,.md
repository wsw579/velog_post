<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/747143db-1b39-4fd8-a80d-792ea962bef1/image.png" /></p>
<p><strong>9/30 - 10/2</strong></p>
<blockquote>
<p>수업을 듣기시작한지 벌써 한 달이 다 되어가네요.
그리고 9월을 지나 벌써 10월이라니 ... ! 
수업을 시작할때만해도 내년까지 기간이 꽤 길다고 생각했는데 한 달이 이렇게 쏟살같이 지나가다니 ... 조금 아쉽기도 하고 흘러가는 시간을 붙잡고 싶을떄도 있네요.
그래도 하루하루 9시부터 6시까지 수업듣고 , 끝나고 운동하고 복습 &amp; 공부하고 하루를 열심히 살았다고 생각한 9월이기에 후회가 남지않고 10월은 더 체계적계획해서 시간을 더 잘 활용하자는 마음만 드네요.</p>
</blockquote>
<h3 id="✅-머신러닝-주요알고리즘">✅ 머신러닝 주요알고리즘</h3>
<h4 id="1-linearregression--선형회귀모델">1. LinearRegression , 선형회귀모델</h4>
<h4 id="2-knn--이웃--분류">2. KNN : 이웃 , 분류</h4>
<h4 id="3-decision-tree--결정트리">3. Decision Tree : 결정트리</h4>
<h4 id="4-logisticregression--로지스틱회귀">4. LogisticRegression : 로지스틱회귀</h4>
<h3 id="✅-k-fold-cross-validation">✅ K-Fold Cross Validation</h3>
<blockquote>
<p>지금까지 공부를위해 [ 학습 - 평가 ] 진행했다.<br />원래 머신러닝과정은 [ 학습 - 검증 - 평가 ] 를 진행해야한다.
이때 검증용데이터는 모델의 일반화된 성능을 예측할 수 있게한다.
하지만 검증용데이터 또한 최종 하나의 데이터에대한 추정일뿐이므로 
정교한 평가절차 필요하다. </p>
</blockquote>
<p>** ❓ 모든 데이터가 한 번은 검증데이터로 사용된다면 정확도가 올라가지 않을까 ❓ <br /> 👉🏻 K-분할 교차 검증이 모든 데이터가 평가에 한 번, 학습에 k-1번 사용한다. **
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/b54c2e46-66be-4186-8ad7-e38771da25ae/image.png" /></p>
<p>📌** 데이터가 많아질수록 반복횟수가 많아서 모델 학습&amp;평가에 많은시간이 소요된다는 단점이 있지만 좀 더 일반화된 모델을 만들 수 있어 정확도를 향상시킬 수 있다.  **
<br /></p>
<h3 id="✅-실습">✅ 실습</h3>
<p>**[1] 분류문제 - MLO4-01 **</p>
<ul>
<li><p>데이터 전처리 中 KNN 알고리즘 사용하기위해서 정규화 진행하기 📌
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/5bab43d3-0c6f-4960-8209-ae704f806732/image.png" /></p>
</li>
<li><p>1) DecisionTree 2) KNN 3) LogisticRegression 각각의 K분할교차검증 평균값 구해서 성능비교하기 </p>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/2913e3b3-1068-4147-9e23-cd3e3f75ac03/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/6eb9069c-1330-4301-b86a-e726a6623dc9/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/b2d54789-12a2-4792-a152-6e09fa627b51/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/21577119-8cae-4272-989a-9706a0ac30d2/image.png" /></p>
<ul>
<li>LogisticRegression 알고리즘이 성능이 가장 좋다 </li>
<li>아직 학습을 안했으므로 학습&amp;평가를 진행하겠다.</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/53183822-52fb-4aa6-8041-e764dfa6c43d/image.png" /></p>
<ul>
<li>평가 정확도 78% </li>
<li>검증 정확도 77% </li>
<li>결과적으로 꽤 비슷한 정확도가 나오긴했다. <br />

</li>
</ul>
<p><strong>[2] 회귀문제 - 실습04-01</strong></p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/7010eaf5-1a2c-4bc4-9d56-311f5eb65ec3/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/d0908f16-1821-456c-a331-fbf276b47f2e/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/c03db437-16b9-49e3-bc89-be03015d2db8/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/4691a07a-5907-482f-9a42-0e59d9d7c2bc/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/2bf1313a-399f-4ea9-9dea-5276690eaa95/image.png" /></p>
<ul>
<li>평가 정확도 83% </li>
<li>검증 정확도 73% </li>
<li>결과적으로 조금 차이가 보인다. </li>
</ul>