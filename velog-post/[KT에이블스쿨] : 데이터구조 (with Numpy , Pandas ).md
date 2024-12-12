<p>*<em>2024.09.06 *</em></p>
<blockquote>
<p>데이터분석 전처리를 위한 numpy,pandas 등 처음배웠을때는 처음보는 내용이라 조금 헷갈렸는데 지금은 그래도 익숙해졌습니다. 
데이터전처리를 자유자재로 할 수 있을 그날까지 ... !!! </p>
</blockquote>
<h3 id="📌-데이터분석에서-가장-중요한-부분--_crisp-dm-_">📌 데이터분석에서 가장 중요한 부분 : _CRISP-DM _</h3>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/7fc467f5-5588-489d-92dd-f88225f53356/image.jpg" /> </p>
<ul>
<li><em><strong>CRISP-DM</strong></em> = 비즈니스 문제해결 방법론 </li>
</ul>
<p>즉, 이 방법론을 구현하기위한 첫번째 단계는 분석을 위한 Data set을 담아내는 데이터구조(자료형)을 알아야한다.</p>
<h3 id="📝-분석모델링-정보종류">📝 분석,모델링 정보종류</h3>
<ul>
<li>범주형 과 수치형 </li>
</ul>
<table>
<thead>
<tr>
<th align="center">📌 데이터 종류</th>
<th align="center">👉 포함되는 데이터</th>
</tr>
</thead>
<tbody><tr>
<td align="center">범주형</td>
<td align="center">분류할 수 있는 데이터 ex) 합격/불합격</td>
</tr>
<tr>
<td align="center">수치형</td>
<td align="center">연속하는 숫자데이터 ex) 160/170/180</td>
</tr>
</tbody></table>
<blockquote>
<p>어떻게 구분해야할까 ❓ 값을 3배 할 수 있으면 수치형 , 할 수 없으면 범주형</p>
</blockquote>
<h3 id="✍🏻-수치형-데이터">✍🏻 수치형 데이터</h3>
<ul>
<li>기본이 2차원 = Array = Table = Data Frame </li>
</ul>
<ol>
<li><p>열 = 정보 = 변수 = 요인(x,feature) , 결과(y,target,label)  </p>
</li>
<li><p>행 = 샘플 = 관측치 = Data point = 분석단위 = 이 단위로 데이터를 보겠다 = 이런관점으로 행이 구성되어있다. 
axis=0 👉🏻 단위데이터의 건수를 의미
🌟 (100,21) 일때 21개의 값으로 구성된 2차원데이터가 100건의 건수가 있다. 
🌟 (1000,28,28) 일때는 (28x28)이런 2차원데이터가 1000건수가 있다. </p>
<br /> 
### 📌 Numpy (수치화 , 배열) </li>
</ol>
<ul>
<li>리스트는 다른타입의 데이터를 한꺼번에 저장하고 , 요소변경&amp;추가&amp;제거가 용이하지만 대량의 데이터의 수학적계산은 불가능하다</li>
<li>이런 한계로 데이터분석시 Array단위로 빠른수차계산을 할 수 있는 numpy사용한다.</li>
</ul>
<pre><code>- numpy 라이브러리 불러오기 

import numpy as np  # as 는 별칭을 붙여주는 것 
from numpy import array # numpy에서 array함수만 불러오기 
</code></pre><h4 id="✅-numpy-용어정리">✅ numpy 용어정리</h4>
<p>Matrix = 행렬이 있을때 </p>
<ul>
<li>Axis = 배열의 각 축 -&gt; axis = 0 (열) , axis = 1 (행)</li>
</ul>
<pre><code>    axis = 0         
    ↓                
    ↓                
    ↓     → →  →   axis = 1         
</code></pre><ul>
<li><p>Rank = 축의 개수(차원) = data frame이면 2차원이므로 2개라고 할 수 있다.</p>
</li>
<li><p>Shape = 축의 길이 = 갯수 (3,4) = 크기를 알려준다. 
🌟 Reshape : 기존배열을 새로운형태의 배열로 다시구성 
대신 배열요소가 사라지지않는 형태에서 변환가능 
ex) 3x4 -&gt; 2x6 -&gt; 12x1 -&gt; 6x2 <br /> 
🌟 a.reshape(3,-1) -&gt; a를 3행으로 된 배열로 변환 ,열의 수는 데이터에 맞게 
= -1은 네가 계산해 ~ </p>
<br /> 
#### ✴️참조 : 알고 있으면 좋은 내용 </li>
<li><p>np.zeros() = 0으로 채워진 배열</p>
</li>
<li><p>np.ones() = 1로 채워진 배열</p>
</li>
<li><p>np.full() =  특정값으로 채워진 배열</p>
</li>
<li><p>np.eye() = 정방향행렬</p>
</li>
<li><p>np.random.random() = 랜덤값으로 채운 배열 </p>
<br />

</li>
</ul>
<h4 id="❓함수와-메서드">❓함수와 메서드</h4>
<ul>
<li>메서드는 함수에 딸린거라고 생각하면 쉽다.</li>
<li>함수 : np.mean() - mean()함수에서 자동으로 np array로 평균을 구해주기때문에 입력값의 데이터형태는 상관이 없다.</li>
<li>메서드 : a.mean() - a는 np array만 사용가능하다. </li>
</ul>
<h4 id="인덱싱">인덱싱</h4>
<p>배열 데이터 조회 : 인덱싱 
🌟 array[0] - 열 인덱스는 생략가능
🌟 array[:,0] - 행 인덱스는 생략불가능 , : (전체조회)
🌟 array[[0,1]] - 행을 가져올때는 이렇게 list로 받아온다. 즉, 결과는 0,1행 전체출력 </p>
<h4 id="npargmax--npargmin">np.argmax() , np.argmin()</h4>
<ul>
<li>가장 큰 값(작은값) 인덱스 반환  </li>
</ul>
<h4 id="npwhere조건문참일때값거짓일때값">np.where(조건문,참일때값,거짓일때값)</h4>
<h4 id="nplinspace">np.linspace</h4>
<ul>
<li>NumPy에서 두 값 사이의 일정한 간격으로 분할된 값을 생성하는 함수이다. </li>
<li>수학적 계산이나 그래프를 그릴 때 유용하게 사용된다.</li>
</ul>
<h3 id="📌-pandas-data-frame">📌 Pandas (Data Frame)</h3>
<p>Pandas | series: data frame의 열을 하나 떼어낸 것(1차원) , data frame : 2차원 
-- 조회ㅣ df.loc[조건문,(뒤에는생략가능)열이름] / df.iloc(인덱스위치로)</p>