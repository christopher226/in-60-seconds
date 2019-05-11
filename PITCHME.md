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

- RandomForest/ExtraTrees
- N_estimators, higher the better
- try 10 and then 300, if you have enough N_estimators, it should be saturated
- max_depth, try 7 first, unlimited in default setting. it may 10, 20 or higher(higher than xgboost
- min_sample_leaf is corresponding to min_child_weight
- criteria: Geni is generally better than Entropy

