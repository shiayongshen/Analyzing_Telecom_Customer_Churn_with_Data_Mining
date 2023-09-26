# 使用資料探勘分析電信客戶流失
本研究將針對電信客戶流失資料集做分析。
本資料集為 Kaggle 平台上位在南加利福尼亞州的某電信公司所提供，含有7043位客戶的電話和網際網路服務資料。此資料集內容包含客戶特徵、選用的服務、流失情形以及使用情況等等。
### 處理資料不平衡
原始資料客戶流失(Churn)欄位中，無流失樣本數為5174筆，流失樣本為3305筆，本研究使用隨機抽樣的上下採樣法，將樣本數過多的無流失資料隨機刪除，並隨機增加流失資料，使資料趨近平衡。
##### 隨機上下採樣前
![image](https://github.com/shiayongshen/Analyzing_Telecom_Customer_Churn_with_Data_Mining/blob/main/dm_pic/before.jpg)
##### 隨機上下採樣後
![image](https://github.com/shiayongshen/Analyzing_Telecom_Customer_Churn_with_Data_Mining/blob/main/dm_pic/after.png)
### 熱力圖分析
![image](https://github.com/shiayongshen/Analyzing_Telecom_Customer_Churn_with_Data_Mining/blob/main/dm_pic/heat.png)
### 決策樹模型
參數設定如下：
```
max_depth = 5
test_size = 0.3
K_fold = 10
#train_size = 0.63, valid_size = 0.07, test_size = 0.3
```
經過交叉驗證後之結果如下：
![image](https://github.com/shiayongshen/Analyzing_Telecom_Customer_Churn_with_Data_Mining/blob/main/dm_pic/dt_ROC.png)
![image](https://github.com/shiayongshen/Analyzing_Telecom_Customer_Churn_with_Data_Mining/blob/main/dm_pic/dt_confusion_matrix.png)
![image](https://github.com/shiayongshen/Analyzing_Telecom_Customer_Churn_with_Data_Mining/blob/main/dm_pic/dt_recall_precision.png)
![image](https://github.com/shiayongshen/Analyzing_Telecom_Customer_Churn_with_Data_Mining/blob/main/dm_pic/dt_avg.png)
![image](https://github.com/shiayongshen/Analyzing_Telecom_Customer_Churn_with_Data_Mining/blob/main/dm_pic/dt.png)
### 羅吉斯回歸模型
參數設定如下：
```
PCA(n_components=14)
test_size = 0.3
K_fold = 10
#train_size = 0.63, valid_size = 0.07, test_size = 0.3
```
經過交叉驗證後之結果如下：
![image](https://github.com/shiayongshen/Analyzing_Telecom_Customer_Churn_with_Data_Mining/blob/main/dm_pic/log_ROC.png)
![image](https://github.com/shiayongshen/Analyzing_Telecom_Customer_Churn_with_Data_Mining/blob/main/dm_pic/log_confusion_matrix.png)
![image](https://github.com/shiayongshen/Analyzing_Telecom_Customer_Churn_with_Data_Mining/blob/main/dm_pic/log_recall_precision.png)
![image](https://github.com/shiayongshen/Analyzing_Telecom_Customer_Churn_with_Data_Mining/blob/main/dm_pic/LOG_avg.png)
### 總結

![image](https://github.com/shiayongshen/Analyzing_Telecom_Customer_Churn_with_Data_Mining/blob/main/dm_pic/dtVSlog.png)
