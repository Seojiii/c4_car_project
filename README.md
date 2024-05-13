인도 중고차 가격 예측 프로젝트
- POS_Cars(주)는 인도 중고차 시장에서 신규 사업을 목표로 하는 신생 스타트업.
- 인도 중고차 시장의 고객들은 가성비가 좋은 차량을 선호.
- POS_Cars(주)는 경쟁력 확보와 수익성 향상을 위해 데이터 분석을 통하여 "핵심영향인자 도출"과 "가격예측모델 개발"을 진행하려 함.

# !sudo apt-get install -y fonts-nanum
# !sudo fc-cache -fv
# !rm ~/.cache/matplotlib -rf
     

import numpy as np
import pandas as pd

import matplotlib as mpl
import matplotlib.pyplot as plt
import seaborn as sns

plt.rc('font', family='NanumBarunGothic')

from sklearn.tree import DecisionTreeRegressor
from sklearn.tree import DecisionTreeClassifier
from sklearn.linear_model import LinearRegression
from sklearn.ensemble import RandomForestRegressor
from sklearn.ensemble import GradientBoostingRegressor
from xgboost import XGBRegressor
from sklearn.metrics import r2_score
from sklearn.preprocessing import StandardScaler
from sklearn.model_selection import train_test_split
from sklearn.model_selection import GridSearchCV

from sklearn.tree import export_graphviz
import graphviz

from scipy import stats
from scipy.stats import ttest_ind

import statsmodels.formula.api as smf
from statsmodels.stats.outliers_influence import variance_inflation_factor
from statsmodels.api import qqplot, add_constant

     

from google.colab import drive
drive.mount('/content/drive')
     
Drive already mounted at /content/drive; to attempt to forcibly remount, call drive.mount("/content/drive", force_remount=True).

%load_ext google.colab.data_table
     
The google.colab.data_table extension is already loaded. To reload it, use:
  %reload_ext google.colab.data_table
Load the Data

df = pd.read_csv("/content/drive/MyDrive/BigData/Car.csv")
df.head()
     # car
