
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


隨機分類.ipynb
-------
直接開啟 `隨機分類.ipynb` 並視需求下載套件
### 輸入訓練集

在這裡`df = pd.read_csv('train ().csv')` 放入預處理過的.csv檔(在`example.csv`裡)，當然也可以加入經過您處理的.csv檔案

### 輸入待預測集
在這裡 ` df_public = pd.read_csv('public.csv')` 放入待預測檔案

如果遇到錯誤請檢查是否有以下問題

1. 是否有將標籤改成大寫
2. 是否有空缺值

model.ipynb
------
直接開啟 `model.ipynb` 並視需求下載套件

於https://drive.google.com/file/d/10GTqZtS9T3Yh2ZJwnW9aji5gG8ca7rCt/view 下載所需要的.joblib檔案



 
