<h5 id="20240912">2024.09.12</h5>
<h4 id="ch3-평균-추정과-신뢰구간-br-분산-br">ch3. 평균 추정과 신뢰구간 <br /> 분산 <br /></h4>
<ul>
<li><h5 id="평균--br-분산--br-표준편차--br-모집단--br-표본--br">평균  <br /> 분산  <br /> 표준편차  <br /> 모집단  <br /> 표본  <br /></h5>
</li>
</ul>
<h4 id="ch4-이변량분석범주---숫자">ch4. 이변량분석(범주 -&gt; 숫자)</h4>
<ul>
<li>1) 시각화 : barplot를 이용해 평균을 비교하고 신뢰구간(오차범위)를 통해 관계여부 파악</li>
<li>두 변수의 평균차이가 크고 , 신뢰구간이 겹치지않을때 대립가설이 맞다고 볼 수 있다(=관계가있다)</li>
<li>2) 수치화 : ttest / anova(분산분석) 을 통해 비교한다<ul>
<li>평균을 비교해 차이 검정</li>
<li>ttest(범주수=2,두그룹간 평균차이비교) / anova(범주수&gt;=3,전체평균과 각그룹평균차이비교)</li>
<li><h5 id="--t통계량-두-그룹-평균차이--se표준오차--🚨-두-평균차이로-이해해도-좋다-br---t통계량-검정은-p-value005-를-통해-한다--🚨절대적인-기준은-아니다-br----t통계량---2-or-t통계량--2-라면-차이가-있다고-본다">- t통계량: |두 그룹 평균차이| / SE(표준오차) ; 🚨 두 평균차이로 이해해도 좋다 <br /> - t통계량 검정은 p-value&lt;0.05 를 통해 한다 ; 🚨절대적인 기준은 아니다 <br /> -  t통계량 &lt; -2 or t통계량 &gt; 2 라면 차이가 있다고 본다</h5>
</li>
<li><h5 id="--anova분산분석--셋-이상-집단-숫자-비교-br---전체평균을-기준으로-여러집단의-평균을-비교한다-br---f-통계량분산비--집단-간-분산--집단-내-분산--br-🚨-집단-간-분산이-커질수록--집단-내-분산이-작을수록-f통계량은-커진다--클수록-차이가-있다-br---f통계량이-23이상이면-차이가-있다고-판단한다-br---문법-ㅣ-f_onewayabc-br">- anova(분산분석) : 셋 이상 집단 숫자 비교 <br /> - 전체평균을 기준으로 여러집단의 평균을 비교한다. <br /> - F 통계량(분산비) = 집단 간 분산 / 집단 내 분산  <br /> ;🚨 집단 간 분산이 커질수록 , 집단 내 분산이 작을수록 F통계량은 커진다 =&gt; 클수록 차이가 있다 <br /> - F통계량이 2,3이상이면 차이가 있다고 판단한다. <br /> - 문법 ㅣ f_oneway(A,B,C) <br /></h5>
</li>
</ul>
</li>
</ul>
<h4 id="ch5-이변량분석범주---범주">ch5. 이변량분석(범주 -&gt; 범주)</h4>
<ul>
<li><h5 id="성별과-생존여부-관련여부">성별과 생존여부 관련여부</h5>
</li>
</ul>
<table>
<thead>
<tr>
<th>성별</th>
<th>생존여부</th>
</tr>
</thead>
<tbody><tr>
<td>남</td>
<td>사망</td>
</tr>
<tr>
<td>여</td>
<td>생존</td>
</tr>
<tr>
<td>여</td>
<td>생존</td>
</tr>
<tr>
<td>남</td>
<td>생존</td>
</tr>
<tr>
<td>남</td>
<td>사망</td>
</tr>
</tbody></table>
<p>*<em>분석방법  <br />1) mosaic : 교차표(crosstab)시각화  <br />2) 카이제곱검정 : 관련없을때 교차표와 차이 비교 *</em></p>
<h4 id="1--mosaic--br-1-1--교차표-pdcrosstab-행열normalize">1)  mosaic : <br /> 1-1 ) 교차표 pd.crosstab (행,열,normalize=)</h4>
<h4 id="normalize-옵션--비율로-변환-👉-columns--열기준100--index행기준100--all전체기준100-br">normalize 옵션 : 비율로 변환 👉 columns : 열기준100% , index:행기준100% , all:전체기준100% <br /></h4>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/f7c414d4-d815-4968-9c68-86bb4b379812/image.png" /></p>
<h4 id="mosaic">mosaic</h4>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/bb5b9cd9-42ed-4e95-9e03-5925fcd1ddbd/image.png" /></p>
<ul>
<li><p>mosaic X축은 Pclass , Y축은 생존여부 </p>
</li>
<li><p>빨간선은 사망자비율평균을 나타낸다.</p>
</li>
<li><p>빨간선을 기준으로 생존여부를 파악할 수 있다. </p>
</li>
<li><p>feature, target 관련이 없다면 1,0비율이 빨간선에 맞춰 형성된다.</p>
</li>
<li><p>100% Stacked Bar
<img alt="" src="https://velog.velcdn.com/images/victoryone/post/fc23c98a-b522-44e9-b946-80df8a97ac2d/image.png" /></p>
</li>
<li><p>normalize = = 'index'를 해서  비율만 비교한다.</p>
</li>
</ul>
<blockquote>
<p>**범주 -&gt; 범주   </p>
</blockquote>
<p>1) 시각화 : mosaic plot **</p>