
# AI-CUP-2023多模態病理嗓音分類
## 作品說明
* [前言](#前言)
* [voice_analysis](#voice_analysis)
* [隨機分類.ipynb](#隨機分類.ipynb)
* [model.ipynb](#model.ipynb)


前言
------
環境介紹
1. numpy  1.22.4 
2. sklearn  0.0.post1 
3. xgboost 0.90
4. pandas 1.5.2 
5. pandasq l0.7.3
6. cx-Orcle 8.3.0 
7. dill  0.3.6
8.  librosa 0.10.0.post2 
9.  tqdm  4.64. 

voice_analysis
------
打開 `voice_model.ipynb` 

於https://drive.google.com/drive/u/0/folders/1cZnhKL_vjyVZlmCnDZsxaYaUVHzrAkWR 下載重新編輯過的聲音，並將它們與`voice_model.ipynb` 放在同一個資料夾。

查看`tmp001.xls`的編號操作

可以清楚的看到多種頻譜圖，並可以藉此找出重要的參數

隨機分類.ipynb
-------
直接開啟 `隨機分類.ipynb` 並視需求下載套件
### 輸入訓練集

在這裡`df = pd.read_csv('train ().csv')` 放入預處理過的.csv檔(在`example.csv`裡)，當然也可以加入經過您處理的.csv檔案

### 輸入待預測集
在這裡 ` df_public = pd.read_csv('public.csv')` 放入待預測檔案

接下來程式會計算各個標籤的重要度
可以直接視需求增減標籤
如果遇到錯誤請檢查是否有以下問題

1. 是否有將標籤改成大寫
2. 是否有空缺值

###輸出

可以於調參程式中使用預設的候選參數當然您也能自行添加

可供調整的參數如下

1. max_depth:樹的最大深度限制，用於控制樹的複雜度和防止過擬合。
2. learning_rate:學習率控制每一步梯度下降的幅度，影響模型的收斂速度和性能。
3. gamma:在樹的生長過程中，只有當樹分裂後損失函數的減少值大於gamma時，才執行分裂操作。
4. subsample: 每棵樹的樣本抽樣率，控制樣本的隨機性，避免過擬合。
5. colsample_bytree: 每棵樹的特徵抽樣率，控制特徵的隨機性，避免過擬合。
6. n_estimators:指定樹的數量，也就是迭代次數，每一次迭代生成一棵樹。

其中`learning_rate` 、`subsample ` 、 `colsample_bytree` 需介於0~1之間

model.ipynb
------
直接開啟 `model.ipynb` 並視需求下載套件

這是添加AR與Hurst進入參數的程式

調參規則參照上述

於https://drive.google.com/file/d/10GTqZtS9T3Yh2ZJwnW9aji5gG8ca7rCt/view 下載所需要的.joblib檔案

