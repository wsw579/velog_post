<h4 id="범주---범주">범주 -&gt; 범주</h4>
<h4 id="2-수치화---카이제곱검정">[2] 수치화 - 카이제곱검정</h4>
<ul>
<li>기대빈도 = 아무련 관련이 없을때 나올 수 있는 빈도수 = 확률적으로 독립일때</li>
<li>즉 , 기대빈도로부터 실제값과 차이가 얼마나 나는건지 카이제곱검정을 통해 알아본다.</li>
<li>카이제곱 통계량(x^2) = 0에 가까울수록 기대값이 실제값과 가깝다 = 관련이 없다.</li>
<li>즉 , 카이제곱 통계량이 클수록 기대빈도로부터 실제값의 차이가 크다 = 관련이 있다. </li>
<li>자유도(F)의 약 2배보다 크면 차이가 있다라고 본다. </li>
<li>자유도 = 범주의 수 -1 , Pclass 범주 =3 , Survived = 2 라고 가정하면 (3-1) * (2-1) 2라는 자유도 결과가 나온다.  </li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/8ad0f348-a28c-4b56-889a-864e4a4bef44/image.png" /></p>
<ul>
<li>카이제곱 검정 결과 : 1)카이제곱 통계량 2)p-value 3)자유도 4)기대빈도 값 </li>
</ul>
<h4 id="ch6-이변량-분석-숫자---범주-br">ch6. 이변량 분석 숫자 -&gt; 범주 <br /></h4>
<ul>
<li>숫자 -&gt; 범주 일때 시각화는 히스토그램 , kde를 사용해 분석한다. </li>
<li>그렇지만 수치화는 정해진 분석방법이 없고 상황에 맞게 사용한다 </li>
<li>ttest ,anova 혹은 숫자를 범주로 바꿔 (pd.cut) 카이제곱검정 혹은  로지스틱회귀를 한다.</li>
</ul>
<h4 id="1-시각화">[1] 시각화</h4>
<h4 id="1-snskdeplot-br-common_norm-false--생존자사망자-각각-그리기-br-mutiple--fill-모든구간에-대한-100-비율로-kde-lot-그리기">1) sns.kdeplot() <br /> common_norm =False : 생존자,사망자 각각 그리기 <br /> mutiple = 'fill' 모든구간에 대한 100% 비율로 kde lot 그리기</h4>
<ul>
<li><p>kdeplot 그래프는 데이터가 없어도 이어서 그려준다. 
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/fb584c20-3b40-4c64-92a0-8bd9ee0771e9/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/f394264d-2c18-4657-b5bf-55f620c106c0/image.png" /></p>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/566769ff-7709-4a79-b10e-bab5b8caff36/image.png" /></p>
<ul>
<li><p>이때 Fare에서 0보다 작은값은 무엇일까 ?</p>
<ul>
<li>이상치 혹은 데이터오류값이므로 0이하값을 제거해서 사용하거나 0으로 처리한다.<h4 id="2-snshistplotxdf">2 sns.histplot(x,df)</h4>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/124db708-a6e7-494b-b376-3b5e164eb203/image.png" /></p>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/b685c819-7e73-464c-9a03-1abe34bab4db/image.png" /></p>
<ul>
<li>bins 개수를 다르게하면 다른모습을 볼 수 있다. </li>
<li>한 가지 그래프만 보고 판단하지말자.</li>
</ul>