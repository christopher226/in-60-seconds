### Coursera Kaggle講座


- "How to win a data scienece competition: learn from top kagglers"
- ロシアのNational Research University Higher School of Economicsが主催
- 講師はKaggleのトップランカー
- アカデミックな内容よりは、Kaggleで勝つためのテクニック
- Data Leakのようなコンペでは発生するが実世界では使えない"邪道"な内容も扱う

---

### 今回の受講内容

- How to deal with Kaggle Competition 
- Advanced feature engineering

---

### How to deal with Kaggle Competition

- Cross Validation Strategy
 - Time-based cross validation
 - Stratified K-Fold
 - Simple  K-Fold
- Test validation strategy itself in test leaderboard

---

### Advanced Feature Engineering

- Stats of
 - groups grouped by pairs of variables
 - neighborhoods defined by
  - ex. houses within 1,000 meters
- Example of neighborhooding strategy(KNN)
 - mean encoding to all variables, enabling to fairly evaluate distance under an appropriate scaling
 - based on Bray-Curtis metrics, selecting 2,000 nearest neighborhood
- Dimentionality Reduction
 - Matrix Factorization
 - PCA NMF
- t-SNE
 - hyperparameter perplexity 5-100
---

### Emsambling

- Averaging
  - Simple/Weighted Averaging
  - Conditional Averaging
- Bagging
- Stacking
 - StackNet
 - K-Fold like mean encoding
- catboost is 30-60 times faster than xgboost, lightgbm

---