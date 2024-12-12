<blockquote>
<p>*<em>미프5차 프로젝트 끝나고 바로 돌아온 미프6차 !!
이번프로젝트는 지금까지 배웠던 부분을 활용하고 새로운데이터인 시계열데이터를 이용해 판매량 예측을하는 프로젝트이다. 흥미로우면선도 시계열데이터를 전처리하고 비즈니스문제를 해결하는데 어려웠다. 팀원들의 도움과 프로젝트 끝나고 개인공부를 하면서 지금은 프로젝트를 이해했고, 해결할 수 있었다 ! 🤗  *</em></p>
</blockquote>
<h2 id="🏪-day-1--데이터-탐색-및-가설-도출">🏪 DAY-1 : 데이터 탐색 및 가설 도출</h2>
<blockquote>
<p><strong>프로젝트 배경소개 :  유통 매장에서 상품별 재고문제 해결 필요</strong>
• 미국 전역에 매장이 있는 유통회사 K-Mart , 매장에는 과재고와 재고 부족 문제 존재
• 수요가 많거나 급증하는 상품: 재고부족
• 수요가 적거나 급감하는 상품: 과재고
• 발주 후 상품은 각각의 리드타임에 맞게 입고된다.  리드타임이 2일 걸리는 상품은, 
5월20일 저녁 10시에 주문하면, 5월22일 새벽(매장 오픈 전)에 입고되어 당일 판매를 할 수 있음</p>
</blockquote>
<ul>
<li>타당성을 검토하기 위해, <strong>가장 매출이 높은 44번 매장에 대해 파일럿 프로젝트 진행</strong>
• 핵심 상품 3개를 선정하고, 이들에 대한 수요 예측을 기반한 발주 시스템의 가능성을 검토
✔️ *<em>핵심 상품 3개 : 농작물 , 우유 , 음료 *</em>
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/95392ec5-5ccb-4b3f-94ab-dce345eb3717/image.png" /></li>
</ul>
<ul>
<li><p>팀원들끼리 핵심상품 3개를 나눠서 데이터 분석 진행</p>
</li>
<li><p>나는 우유 🥛 (Product_ID = 12)를 분석했다. </p>
</li>
<li><p>** 🥛 데이터 탐색, 가설수립, 데이터셋 구성 ** </p>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/006c96df-e15b-4b1a-8d8c-202c03cc2172/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/06e424c4-b984-46d7-a3ca-c1fc200f8229/image.png" /></p>
<blockquote>
<p>** 전체데이터 연도별,월별 🥛 판매추이 : 연말에 가장 많이 구매  &amp;  소비량이 점점 많아진다. **</p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/e830395d-e6c1-43d1-8af7-36e21bbd67ab/image.png" /></p>
<blockquote>
<p><strong>우유와 같은 카테고리 상품 판매추이 : 우유만 독보적인 판매량을 보인다.</strong></p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/2016143d-39cf-49e8-8fa8-fee05988df70/image.png" /></p>
<blockquote>
<p>** 🥛 월별 , 요일별 판매추이 **</p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/a08f26f2-68e9-40c5-bcd6-c4bdd2b28b44/image.jpg" /></p>
<blockquote>
<p>*<em>방문수와 우유판매량 상관관계 *</em></p>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/693fa130-f7dc-4969-b99e-a87b7c237c28/image.jpg" /></p>
<blockquote>
<p>*<em>유가와 우유판매량 상관관계 *</em></p>
</blockquote>
<h2 id="🏪-day-2--데이터-전처리-및-base-line-모델-생성">🏪 DAY-2 : 데이터 전처리 및 base line 모델 생성</h2>
<ol>
<li><p>date 데이터 처리 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/29051cb9-9be4-4d2b-8a73-1e28a3614b31/image.png" /></p>
</li>
<li><p>전체데이터 中 44가게 , 우유 🥛 데이터 추출
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/c710bde7-3d80-4a8a-a294-a07d3519f320/image.png" /></p>
</li>
<li><p>시계열데이터 추가</p>
</li>
</ol>
<blockquote>
<p>*<em>data['y'] = data['Qty'].shift(-2) # y : 2일 후 판매량
data['Qty_MA7'] = data['Qty'].rolling(7, min_periods = 1).mean()
data['y_day'] = data['WeekDay'].shift(-2) # y : 2일 후 판매량 요일 : 우리가 예측할 값
*</em></p>
</blockquote>
<ol start="4">
<li><p>전체 데이터셋 구성
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/a0eb0269-fc3c-47d7-8667-8160a58cf04f/image.png" /></p>
</li>
<li><p>컬럼삭제 및 y값 = 2일 후 판매량 요일 데이터셋 구성
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/e2ceedba-3806-4eed-a429-6ab0766ae629/image.png" /></p>
</li>
<li><p>LSTM base 모델:<img alt="" src="https://velog.velcdn.com/images/victoryone/post/f7d59c35-d42a-4117-9bf1-907e62b39e59/image.png" /></p>
</li>
</ol>
<ul>
<li>예측값 &amp; 결과값 그래프 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/80e3b4fc-7332-44b2-8c8c-51723fc9888c/image.png" /></li>
</ul>
<blockquote>
<p>** MAE: 1885.8299641927083 : 예측값과 1885개 차이난다는 결론** 
기본모델로 예측했는데도 성능이 꽤 잘나온 것 같다. </p>
</blockquote>
<h2 id="🏪-day-3---모델링-및-비즈니스-평가">🏪 DAY-3 :  모델링 및 비즈니스 평가</h2>
<ul>
<li><p>*<em>비즈니스 관점에서 문제해결 및 설명 *</em></p>
</li>
<li><p>*<em>MAE :  1073.583644701087 : 최종적으로 줄인 MAE값 *</em></p>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/bd00fbd4-333b-4eb8-b226-d1baec767c64/image.png" /></p>
<blockquote>
<p>*<em>결론적으로 기회손실 수량 0으로 만드는 일평균 재고량은 약 14744 개 나왔다.
기록하면서 공부를 다시하고 결과를 다시보니 일평균 재고량이 많다고 생각했는데 그래도 일평균 재고회전율도 괜찮고 괜찮은 결과가 나온 것 같다. *</em> </p>
</blockquote>