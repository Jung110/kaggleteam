# Kaggle Team

## 이름 정의의 대략적인 예

- col명의 경우 명사를 사용한다.  또한 label_encoder을 사용한 col명은 id를 붙인다.
  - ex ) high_category_name  , city_id
- 함수명의 경우 명령문을 형태를 띄여야 한다.(대체로 동사로 시작)
  - clean_text , make_high_category ,add_shop_id
- 변수명의 경우 명사이고, 줄임말로서 줄일 경우 3~4글자로 줄이고, 저장되어있는 데이터를 나타내여야 한다.
  - data_id  ,data_name , item_month_revenue

## 변수명 정리

### 메인 데이터 변수

- items = pd.read_csv("./data/items.csv")
- shops = pd.read_csv("./data/shops.csv")
- train = pd.read_csv("./data/sales_train.csv")
- test = pd.read_csv("./data/test.csv")
- item_categories = pd.read_csv('./data/item_categories.csv')
- submission = pd.read_csv("./data/sample_submission.csv")
- item_high_categories: 아이템괴 아이템 카테고리, 아이템 상위 카테고리를 가진 데이터 프레임
- salse_df : 최종적으로 전처리가 종료된 데이터
- x_train : 훈련용 데이터
- x_valid  : 검증용 데이터
- x_test : 테스트용 데이터

### 중간에 사용한 변수

- condition_for_drop : 
  - drop을 하기위한 조건을 저장하는 변수 
- shops_names : 
  - shops["shop_name"]를  저장하기 위한 변수
- shops_id: 
  - shops["shop_id"] 저장하기위한 변수 
- diff_test_train_shop_id ,diff_test_train_item_id,diff_test_items_item_id: 
  - 각각 train,test 값의 가게 아이디 , 아이템아이의 차이를 알기위해 임시로 사용한 변수
- temp_train:
  - 임시로 train값을 저장하기 위한 변수
- train_item_cnt_month:
  - 한 달간 데이터를 종합할 때 사용한 변수
- item_categories_value_counts:
  - 아이템 상위 카테고리의 value_counts를 저장하는 변수
- temp_data_for_plot:
  - 그래프를 위해 임시로 만든 데이터가 저장되어 있는 변수

## 함수 정리

- price_item_cnt_day_boxplot() - > None
  
  - 아이템 갯수별 가격 박스 플롯 출력하는 함수 

- clean_text(inputString) ->str
  
  - 입력받은 문자열에서 특수 문자를 제거하는 함수 

- make_high_category(data_name_col):
  
  - 상위 분류를 생성후 라벨 인코딩을 하는 함수

- submission

## 사용 모듈

#### 라벨인코딩

from sklearn.preprocessing import LabelEncoder

#### 그래프

import matplotlib.pyplot as plt

#### 기본

import numpy as np
import pandas as pd
import seaborn as sns

##### 함수 사용시 사용

import re

from itertools import product