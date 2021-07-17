
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
Methods:  
fit: 放入X、y進行模型擬合。  
predict: 預測並回傳預測類別。  
score: 預測成功的比例。   
predict_proba: 預測每個類別的機率值。  
  
### SVM 
說明:  
*  將線性不可分的資料投射到較高維度的空間，產生一個可分開兩群資料的平面，並透過計算兩群資料到該平面的margin找出最佳平面，以分割兩群資料。  

參數說明:  
1. kernel='linear' (線性)  
    *    C: 限制模型的複雜度，防止過度擬合。  
    *    kernel: 此範例採用線性。  
2. kernel='poly' (非線性)  
    * C: 限制模型的複雜度，防止過度擬合。    
    * kernel: 此範例採用 Polynomial 高次方轉換。    
    * degree: 增加模型複雜度，3 代表轉換到三次空間進行分類。    
    * gamma: 數值越大越能做複雜的分類邊界。  
3. kernel='rbf' (非線性)  
    * C: 限制模型的複雜度，防止過度擬合。  
    * kernel: 此範例採用 Radial Basis Function 高斯轉換。  
    * gamma: 數值越大越能做複雜的分類邊界  
    
注意事項:  
1.    用於小樣本、非線性、高維度、局部最小點、
1.    訓練時需特徵縮放。  
    
Reference:  
https://github.com/andy6804tw/2020-12th-ironman/blob/master/13.SVM(%E5%88%86%E9%A1%9E%E5%99%A8)/13.SVM(Classfication-iris).ipynb  


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
