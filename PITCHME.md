### Regularization

- Mean Target Encoding
 - Leakを生じさせてしまうのでFoldに合わせたencodingが必要
- Noise
 - noiseを加える
- Expanding Mean Target Encoding
 -カテゴリ内でその行より前までの平均をとる

---

### Hyperparameter Tuning
- Hyperparameter tuningの方法をモデル/ライブラリごとに学ぶ
- 大きくなるほどmodelを制約するもの、逆に柔軟にするものに分類できる
- 柔軟になる程overfittingが起きやすくなる、逆に制約されるほどunderfittingが起きやすくなる
- overfitting/underfittingどちらが生じているか見極めながらparameterを探査する
- hyperparameter探査を自動で行うライブラリもあるが、手作業でやることが多い

---

### GBDT models (XGboost/Lightgbm)
- min_child_weight: 重要 0,5,15,300くらいの順で試す
- eta: 小さい値(0.1か0.01)から試して、徐々に大きくしていく
 - etaをx倍、learning rateを1/xするとスコアが改善する場合が多い
- random seedをいくつか試して結果が変化しないことを確認すること

---

### RandomForest/ExtraTrees
- N_estimators: 大きい方がいいが時間がかかる。一定の値より大きいと効果は逓減する。
 - 10,300の順で試す。N_estimatorsとモデルの精度をプロットし、十分に精度が出る値で止める。
- max_depth: 標準では制約なし。まず7を試し、10,20といった具合に増やしていく。
 - xgboostより深めになることが多い
- min_sample_leaf: xgboostのmin_child_weightと同じ
- criteria: Geni係数の方がEntropyより良いことが多い
- n_jobs: 使用可能な上限コア数に設定する（defaultは1）

---

### Neaural Networks
- まずoverfitさせてからモデルに制約をかけてunderfitさせていく
- Opotimization Algorithm: SGD+momentum or Ada/AdaDelta
 - SGD+momentumの方がoverfittingしないので良い
- Batch size: 500だと大きすぎる。32か64から始めると良い。
 - あまり小さいとgradientにノイズが含まれすぎるのでほどほどに。
- learning rate: まず0.1を最初に試して、徐々に小さくしていく
- バッチサイズをx倍にする時は、learning rateもx倍にする
- Dropout: データの近くのレイヤーをdropoutするとデータの情報が削ぎ落とされるてパフォーマンスが落ちるので、中間のレイヤーに適用する