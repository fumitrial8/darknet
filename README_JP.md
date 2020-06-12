# DEMO
後日追加
 
# Features
* darknetのファイル構成をシンプルに再構築 
 
# Requirement  
* 後日追加
 
# Installation
 
```bash
pip install -r requirements.txt
```
 
# Usage(簡易的に使用する場合)

1. リポジトリをクローン 
```bash
git clone git@github.com:fumitrial8/darknet.git
cd darknet
```

2. 学習済みモデルのダウンロード
(yolov4.weight)[https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.weights]

3. Makefileを修正
環境に応じて以下の設定を変更
* GPUを使ってスピードを上げる場合
```Makefile
GPU=1
CUDNN=1
```

* さらにスピードアップする場合(GPUがVolta, Xavier, Turing and higherの場合)
```Makefile
CUDNN_HALF=1
```

* CPU上でスピードを上げる場合
```Makefile
AVX=1
OPENMP=1
```
エラーが出る場合はOPENNMP=0

* pythonファイルで動かす場合
```Makefile
LIBSO=1
```
これでmakeコマンドを使うとエラーが吐き出されるが、libdarknet.soというファイルが作られるので
pythonコマンドが使える様になる


4. ターミナル上で実行

```bash
make
# Makefileと同じ階層で以下のコードを実行すると、./test.jpgの物体検出が実行される
./darknet detector test cfg/coco.data cfg/yolov4.cfg yolov4.weights -ext_output data/dog.jpg
```


# Usage(オリジナルデータの学習)


