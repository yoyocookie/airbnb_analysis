# Airbnb 新用戶首次預訂國家分析 (Kaggle 比賽專案)

這是針對 Kaggle Airbnb 新用戶預測競賽所進行的資料分析與建模專案。目標是預測新用戶的第一次預訂目的地國家，並使用多種機器學習模型進行比較與優化。

## 📦 專案內容

- 比賽連結：[Airbnb New User Bookings | Kaggle](https://www.kaggle.com/competitions/airbnb-recruiting-new-user-bookings)
- 任務類型：多分類預測（12 個可能國家）
- 評分標準：Normalized Discounted Cumulative Gain (nDCG)

## 🔄 專案流程

1. 透過 Kaggle API 下載資料
2. 進行 EDA 與資料視覺化
3. 資料前處理（缺失值處理、離群值處理）
4. 使用 CatBoost、XGBoost、H2O AutoML 等模型建模
5. 調整參數（包含 Grid Search、Random Search、貝葉斯最佳化）
6. 上傳預測結果至 Kaggle

## 📊 資料介紹

- **輸入資料**：用戶基本資料、瀏覽行為、統計資訊
- **輸出目標**：預測使用者首次預訂的目的地（共 12 類）
  - 如：US、FR、NDF、other 等

## 📈 EDA 與資料視覺化

使用 `matplotlib` 和 `seaborn` 繪製特徵分布圖、correlation matrix、簡單線性回歸與 p-value 分析進行特徵選擇與共線性分析。

## 🧹 資料前處理

- 缺失值填補與離群值處理
- 使用 K-means 分群進行資料清理
- 使用分層抽樣將資料切分為訓練集與驗證集

## 🧠 模型建構與調參

### 🔹 CatBoost

- 建立模型，調整參數（Grid、Random、Bayesian Optimization）
- 上傳預測結果至 Kaggle

### 🔹 XGBoost

- 使用 frequency encoding 處理類別變數
- 同樣進行多種參數搜尋並上傳預測結果

### 🔹 H2O AutoML

- 使用 Target Encoding 處理類別變數
- 採用 H2O 自動訓練模型（包含 GBM、XGBoost、DRF、DeepLearning、StackedEnsemble）

## 🏆 模型表現比較

| 模型        | nDCG 評分 |
|-------------|-----------|
| CatBoost    | 0.8702    |
| H2O AutoML  | 0.8690    |
| XGBoost     | 0.8567    |
| **Best Score on Kaggle** | 0.8870 |

## 🔍 特徵重要性

- **CatBoost**：age, signup method, secs_elapsed
- **XGBoost**：signup method, gender, age
- **H2O**：age, signup method, gender

## 📚 使用的演算法與工具

- Boosting：XGBoost、CatBoost
- 分群：K-means、DBSCAN
- 自動建模：H2O AutoML
- 視覺化：matplotlib、seaborn

## 🧪 程式碼連結

- 📦 資料處理： [Colab Link](https://colab.research.google.com/drive/1AlNslZ1xyrEldfjKXJxh2UoykWx0Lz3w)
- 🤖 模型建構： [Colab Link](https://colab.research.google.com/drive/1O32d01M6wpF_IAH56uFjMVTf4kPBT2n_#scrollTo=GQvqxG2arzW7)


