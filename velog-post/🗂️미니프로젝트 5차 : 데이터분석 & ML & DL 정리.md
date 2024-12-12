<blockquote>
<p>!pip install seaborn # seaborn 설치
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt 
%matplotlib inline   # 주피터 노트북에서 그래프나 시각화를 내장된 형태로 바로 표시
import seaborn as sns
pd.read_csv('파일이름.csv')
df.head() # 디폴트로 상위 , 하위 5줄 보여줌
df.tail()
df.info() # 데이터프레임 정보 : 컬럼정보 , 데이터 수 , 데이터 타입 , null 개수 
df.index  # 데이터프레임 인덱스 정보 : 인덱스 범위와 규칙적인 인덱스 구조
df.columns 
df.values
df.describe() # 데이터프레임 통계치
df.isnull().sum() # null 존재 및 합계
df['컬럼']  # 컬럼 데이터 확인 # 전체 열을 출력
df['컬럼'].unique() # 중복된 값 제거 
df['컬럼'].value_count<strong>s()</strong> # 컬럼 데이터 별 건수 
df['voc_trt_perd_itg_cd'].value_counts(<strong>normalize = True</strong>) # 비율 구해줌
df.drop(columns = '컬럼', inplace=True) 
= df.drop('컬럼' , axis=1 , inplace=True)
col = ['컬럼1'  , '컬럼2' , '컬럼3'  , '컬럼4' , '컬럼5']
df.drop(col, axis=1, inplace=True) # 여러개 col 삭제 
(df['cust_clas_itg_cd'] == '<em>').sum()
= df['cust_clas_itg_cd'].value_counts().get('</em>') # '<em>' 개수 확인 
df.replace('</em>', np.nan) # 값 변경 
df.dtypes # 컬럼 타입확인
df['컬럼'] = pd.to_numeric(df['컬럼'], errors='coerce') # pd.to_numeric : 문자열을 숫자형으로 변환하는 함수 , errors='coerce': 숫자가 아닌 값들 NaN으로 변경
df['컬럼'].fillna(df['컬럼'].median(), inplace = True) # NaN 값 중앙값으로 
df = df.astype({'컬럼': 'int'}) 컬럼 값들 int형으로 변경 
! pip install scikit-learn
cat_cols = df5.select_dtypes(include='object') # select_dtypes() # 특정 데이터 타입을 선택하는 함수
le = LabelEncoder()
df5['cust_clas_itg_cd'] = le.fit_transform(df5['cust_clas_itg_cd'])</p>
</blockquote>
<blockquote>
<p>✔️ <strong>df4 = df3</strong>  , *<em>df5 = df3.copy() 차이점 *</em></p>
</blockquote>
<ul>
<li>df4 = df3          # 참조 ( 얇은 복사 : df3도 함께 변경됨 ) </li>
<li>df5 = df3.copy()   # 복사 ( 깊은 복사 :  df5는 변경되지 않음) </li>
</ul>