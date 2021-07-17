
# Kaggle Pratice

## Predicting Churn for Bank Customers  
### 銀行顧客流失預測  
https://www.kaggle.com/adammaus/predicting-churn-for-bank-customers  

失效正確率:79.4%  
正確率: 86.97%
模型選擇: XGBOOST  
  在一開始取得資料後即開始做特徵的檢查，像是檢查特徵是否有極端值，標籤型特徵的encoding，但直到做了各個特徵和流失者的比較圖才發現，事前的特徵分析仍有許多可分析的價值，例:流失者的年齡分佈普遍較為發散，代表銀行在中老年的族群策略可能需要進行調整。  

  
![image](https://user-images.githubusercontent.com/34003955/124261984-0c081180-db64-11eb-9473-95661273f76d.png)
  
  
  
  
## Heart Failure Prediction  
### 心臟衰竭預測  
https://www.kaggle.com/andrewmvd/heart-failure-clinical-data  

失效正確率:61.67%  
正確率:90%  
模型選擇:Bagging-子模型XGBOOST   
  在觀察特徵時會發現在serum creatinine的分配嚴重向右偏，代表擁有較大極端值，若非該領域的專業，將無法判但是否該剃除，或使其常態化，這裡我選擇先保留並另外建立一份經過log1p的資料，再尋找是否有該指數的說明可參考。  
  每個模型特性皆不同，且調整參數或資料的過程中，也意識到了自己往往會不小心掉入「依據結果來進行調整」的陷阱，因此從一開始的亂調，到後來改為搜尋模型的特性，以明白什麼該對資料和參數做怎樣的調整，即便正確率可能反而下降，但至少可避免運氣好的現象發生。  

![image](https://user-images.githubusercontent.com/34003955/124262095-2fcb5780-db64-11eb-8a8a-4562cff39db5.png)

# 演算法簡述  

## Classfier    
### SVM 
#### 算法說明:
#### 參數說明:
#### 注意事項:
小小樣本、非線性、高維度、局部最小點、訓練時需特徵縮放。
===
### Logistic  
### KNeighborsClassifier   
### DecisionTreeClassifier  
### RandomForestClassifier  
### SGDClassifier  
### MLPClassifier  
### AdaBoostClassifier  
### XGBClassifier  
### CatBoostClassifier  
### BaggingClassifier  

## Regression  


## Reference:
pyinvest:  https://pyecontech.com/  
10程式中:  https://www.youtube.com/channel/UCSNPCGvMYEV-yIXAVt3FA5A  
