<ul>
<li>** 9/9 - 9/10  **</li>
</ul>
<blockquote>
<p>데이터처리</p>
</blockquote>
<h3 id="groupby">groupby</h3>
<p>df 변경</p>
<h3 id="concat--merge">concat / merge</h3>
<p>시계열 데이터<br />: 행과 행 사이 시간순서가 있고 + 그 시간순서의 간격이 동일한 데이터를 의미한다.
    - 날짜 -&gt; 날짜요소를 추출할 수 있다.
    - 시계열데이터 이기때문에 가능한 작업이 있다: shift , rolling , diff (시계열데이터가 아니면 안된다 !!!)
    - shift : 정보 밀고 땡기기 
    - rolling : 시간에 흐름에 따른 평균
    - diff : 특정시점 데이터,이전시점데이터와 차이 구하기 </p>
<h3 id="⭐-데이터분석방법론">⭐ 데이터분석방법론</h3>
<ul>
<li><h5 id="data분석모델링을-할-때는-비즈니스-문제해결을-할-수-있게-해야한다-비즈니스-문제해결-방법론에서-가장-널리-사용되는-방법론은-crisp-dm-이다">data분석&amp;모델링을 할 때는 비즈니스 문제해결을 할 수 있게 해야한다. 비즈니스 문제해결 방법론에서 가장 널리 사용되는 방법론은 CRISP-DM 이다.</h5>
</li>
</ul>
<p><img alt="CRISP-DM" src="https://velog.velcdn.com/images/victoryone/post/558e74b1-100f-431d-a15e-6848d7ca6c6e/image.jpg" /></p>
<h6 id="📌-crisp-dm-데이터분석방법과-관련된-뉴스br--httpswww2ecokrnewsarticleviewhtmlidxno301010-br-마지막구절이-인상깊다-데이터가-축적될수록-분석의-의미중요성은-커지고-전통적인-데이터분석방법인-crisp-dm-과-kdd-둘-다-아직-사용되고-있다는-점이-흥미롭다">📌 CRISP-DM 데이터분석방법과 관련된 뉴스  <a href="https://www.2e.co.kr/news/articleView.html?idxno=301010">https://www.2e.co.kr/news/articleView.html?idxno=301010</a> : 마지막구절이 인상깊다. 데이터가 축적될수록 분석의 의미,중요성은 커지고 전통적인 데이터분석방법인 CRISP-DM 과 KDD 둘 다 아직 사용되고 있다는 점이 흥미롭다.</h6>
<h4 id="✅-1business-understanding--가설-수립">✅ 1.Business UnderStanding : 가설 수립</h4>
<pre><code>- 무엇이 문제인가 ? 
- 데이터분석 &amp; 모델링을 하는 이유 즉, 문제정의
- 문제정의에 맞게 데이터분석방향 &amp; 목표결정
- 초기 가설 수립 X(Y를설명하기위한요인) -&gt; Y(해결할문제,목표,관심사)</code></pre><br />

<p>  $$X (통화량 , 소득수준 , 성별 ...)
  -&gt; 
  Y (이탈여부)
  $$ </p>
<h6 id="👉-통화량에따라-이탈여부와-관계가-있다">👉 통화량에따라 이탈여부와 관계가 있다.</h6>
<h4 id="✅-2data-understanding--데이터-파악">✅ 2.Data Understanding : 데이터 파악</h4>
<pre><code>- 데이터 원본 식별 
📍 있는데이터 - 있는그대로 or 가공해서
   없는데이터 
   - 취득가능 - 취득비용산정(돈)&amp;과제수행(시간)
   - 취득불가능 - 정보의 의미 정의 : 정보를 분할 해 최대한 가용한 데이터로 만들기           
- 데이터 탐색 : EDA / CDA 
    - EDA : 탐색적 데이터 분석 
      방법 | 통계량 또는 그래프 
    - CDA : 확증적 데이터 분석 
      방법 | 가설검정 
      📌이때 사용하는 데이터들은 2차원구조의 데이터셋이다. 
          pd.concat / pd.merge 를 통해 만들어진다. 
    - EDA &amp; CDA 는 단변량분석 -&gt; 이변량분석1 -&gt; 이변량분석2로 진행한다.             
    1) 단변량분석 : 개별변수(열) 분포 
    2) 이변량분석1 : X와 Y 간 관계 (가설확인단계)</code></pre><h4 id="✅-3data-preparation--데이터-정리하자">✅ 3.Data Preparation : 데이터 정리하자</h4>
<pre><code>- 모든셀은 값이 있어야하고 그 값은 숫자여야한다 -&gt; 결측치 조치 
- (옵션) 값 범위 일치시키기 
- 즉, 이 과정에서 수행되는내용 
    1) 결측치 조치
    2) 가변수화
    3) 스케일링
    4) 데이터 분할 </code></pre><h4 id="✅-4modeling">✅ 4.Modeling</h4>
<p><br />시각화 라이브러리
<br />단변량 분석 - 숫자형
<br />단변량 분석 - 범주형</p>