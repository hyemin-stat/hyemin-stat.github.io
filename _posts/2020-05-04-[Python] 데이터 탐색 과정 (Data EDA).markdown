---
title:  "[Python] 데이터 탐색 과정 (Data EDA)"
excerpt: "EDA 과정 정리"

categories:
  - Blog
tags:
  - Blog

date: 2020-05-04 06:00:00 +0000
last_modified_at: 2020-05-04 06:00:00 +0000
---

# import library
##### 기본 library
import pandas as pd
import numpy as np
import scipy #과학기술계산을 위한 Python 라이브러리
import scipy.stats

##### plotting
import matplotlib as mlp
import matplotlib.pyplot as plt
import seaborn as sns
%inline

##### others
import warnings
warnings.filterwarnings('ignore')



# Data 확인
##### Data Load 및 기본 사항 확인
df = pd.read_csv(경로, parse_dates=['datetime64 type으로 호출하고싶은 col명'])<br>
df.head(n) / df.tail(n) # df의 상위/하위 n개 row 확인<br>
df.columns() # df col 이름 출력<br>

 
##### Data Type 확인
cf. python data type<br>
  문자형 - object(pandas), string(python) <br>
  int형 - int64, int32 <br>
  float형 - float64, float32<br>
  bool형 - True, False<br>
  
df.info() # 데이더 전체 확인<br>
df.dtypes() # 데이터 타입 확인<br>
df['col'] = df['col'].astypes('') # 데이터 자료형 변경<br>
 cf. np.int64, np.string, float, int, str, object 가능 (확인 필요함)<br>
 
#####
df.index
 
# 분포 확인
1. y분포
1) 범주형 변수
- 수치
- 그래프
col.value_counts().plot(kind='bar')

2) 연속형 변수
sns.distplot

2. x분포
1) 범주형 변수
cate_features = [col for col in df.columns if df['col'].dtypes='object']
for col in cate_features (??)


# python 함수
##### 정렬하기
df.sort_index(axis=0(행정렬)/1(열정렬),
ascending=True(오름차순)/False(내림차순), 
na_position='first'(NA값을 가장 상단으로))


# Reference
[scipy](https://wikidocs.net/15636)
