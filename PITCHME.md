### Regularization

- Mean Target Encoding
- Noise
- Expanding Mean Target Encoding

---

### Hyperparameter Tuning

- GBDT XGboost/Lightgbm
- min_child_weight
- learning rate eta: try small enogugh learning rate first, 0.1 or 0.01
- x times number of steps and 1/x times eta, leading to better scores
- check robustness to different random seeds

---

###  RandomForest/ExtraTrees
- N_estimators, higher the better
- try 10 and then 300, if you have enough N_estimators, it should be saturated
- max_depth, try 7 first, unlimited in default setting. it may 10, 20 or higher(higher than xgboost
- min_sample_leaf is corresponding to min_child_weight
- criteria: Geni is generally better than Entropy
- n_jobs: do not forget to set as num of cores

### DNN
-overfit to underfi
-optimization
-SGD+momentum or Ada/AdaDelta
-Batch size: Do not use too large batch size 500, leading to overfitting, 32 or 64 is appropriate to start with
-too small batchsize leads to noisy gradietns
-learning rate: try 0.1 first and decrease it untile you find the best fitted one
-x times batch size and x times learning rate at the same time
-Dropout: do not set dropout layer immediately after the data input