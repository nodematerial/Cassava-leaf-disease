# Cassava_leaf_disease
<img src="figure/titlefigure.png">
Kaggle diary for Cassava Leaf Disease Classification.

このリポジトリはCassava Leaf Disease ClassificationのKaggle日記です。

### コンペ情報
画像分類コンペ、タピオカの葉の画像から、病気の状態を予想する。病気の種類は、正常な状態を含めて5つ存在する。

## Timeline

1/22 (本格的に)joined
2/19 deadline
##　目標
1/24時点
金　上位16
銀　上位153
銅　上位306
最低でも銅メダルは取りたい。expert目指すことも考えたら銀も狙いに行かないと。

##　結果
1694/3900(公開カーネル)<br>

途中で面倒くさくなってKaggle日記を書くことはやめてしまったが、ensemble(黒魔術)やaveragingなど、様々な手法を試してみた。Vision Transformerはあまり役に立たなかった。<br>
結局つよつよ公開カーネルに勝てませんでした...

### 1/24
***
一応Notebookは完成したが、なぜかtrain_lossとvalidation_lossが反対に動いてしまう...
<img src="figure/train.png" width="300" height="200">
<img src="figure/val.png" width="300" height="200">

### 1/31
***
紆余曲折を経て、バグを取り除くことに成功した。加えて、自分が納得の行く画像分類タスク用のpipelineを得た。
やっとスタートラインに立てた気がする。

|experiment_name |experiment_1_ResNext|
|----|----|
|model_arch |resnext50_32x4d|
|img_size |256|
|epochs |15|
|train_bs |32|
|valid_bs |32|
|T_max|15|
|lr|0.0001|
|num_workers |2|

|result |experiment_1|
|----|----|
|train_loss|0.2711|
|valid_loss|0.4091|
|train_accuracy|0.9051|
|valid_accuracy|0.8654|

とりあえず実験はうまくいった

### 2/1
|experiment_name |experiment_1_tf_Efficient_b4|
|----|----|
|model_arch |tf_efficientnet_b4|
|img_size |256|
|epochs |15|
|train_bs |32|
|valid_bs |32|
|T_max|15|
|lr|0.0001|
|num_workers |2|

|result |experiment_2|
|----|----|
|train_loss|0.3121|
|valid_loss|0.3416|
|train_accuracy|0.8925|
|valid_accuracy|0.8883|






