<div align="center"></div>
<div align="center">
<img src="https://user-images.githubusercontent.com/49775901/177437930-5b03d608-56fb-4349-afb3-006e06ae7d4a.gif" height=60>
<img src="https://user-images.githubusercontent.com/49775901/177435525-71c41541-4b9a-4ae3-8e6a-996372167f56.png" height=60>
<img src="https://user-images.githubusercontent.com/49775901/177437930-5b03d608-56fb-4349-afb3-006e06ae7d4a.gif" height=60>
</div>

# Description

深層学習を用いて音楽の感情認識を行います。

# Result
推論精度

<img src="https://user-images.githubusercontent.com/49775901/179499393-a452715d-80af-4195-840f-e8f889fe879e.png">

精度

<img src="https://user-images.githubusercontent.com/49775901/179499704-9f58246d-6813-4e8a-9b5f-b02a2052769d.png">

損失

<img src="https://user-images.githubusercontent.com/49775901/179499719-9522e970-eaf6-4e26-a2c6-52267f44f8c9.png">

# Files
latest update: 7/18
<pre>
├─util                                 // モデルで推論するためのプログラム、フォルダの圧縮するためのプログラム、データの可視化プログラム
│  └─visualization_for_docs
├─src                                  // データセット生成とモデルの学習関係
│  ├─my_model                          // マルチモーダルなモデル
│  ├─train_melspec                     // 特徴量にmel-spectrogramを用いるモデル
│  ├─train_stft                        //        STFT
│  │  ├─train_efficient_net_v2         // 特徴量: STFT モデル: EfficientNetV2
│  │  ├─train_mnist                    // 特徴量: STFT モデル: 授業で使ったCNNのやつ
│  │  └─train_VGG16_configured         // 特徴量: STFT モデル: VGG16
│  ├─train_1d_data                     // 特徴量: 一次元特徴量 26個くらい
│  ├─train_logmelspec                  // 特徴量: log10したmelspectrogram
│  └─make_datasets                     // データセット生成関係　2s は make_dataset の中に含まれる
│      └─stft
├─trash　　　　　　　　　　　　　　　　　 // ごみ。（雑日本語訳みたいになってしまった。。。）
├─MER_audio_taffc_dataset_wav          // データセットフォルダ。リポジトリに含まれない。権利関係嫌なので。僕の書いたコード使いたい場合、この構造にすれば動くはず。
│  ├─Q1                                // もとのデータ達
│  ├─Q2                                // もとのデータ達
│  ├─Q3                                // もとのデータ達
│  ├─Q4                                // もとのデータ達
│  ├─renamed                           // 感情.ファイル名.wav にリネームしたやつ
│  ├─2s                                // 2sec 関連
│  │  ├─stft_crop_0.2                  // 地方会のやつ見て
│  │  ├─stft_crop_0.1                  // 地方会のやつ見て
│  │  ├─stft_crop_0.15                 // 地方会のやつ見て
│  │  ├─stft_img                       // STFT画像 jpeg は研究に向いてないと思う（圧縮されてしまうので）。作ったの僕だけど。
│  │  ├─Q1                             // 2sec の wav
│  │  ├─Q2                             // 2sec の wav
│  │  ├─Q3                             // 2sec の wav
│  │  ├─Q4                             // 2sec の wav
│  │  ├─unknown                        // 未知データ
│  │  ├─unknown_img                    // 未知データのSTFT jpeg
│  │  ├─melspectro_img                 // メルスペクトロ.jpg
│  │  ├─unknown_spectro                // 未知のメルスペクトロ.jpg
│  │  ├─log-melspectro_img             // log-melspectro.jpg
│  │  ├─pickles1                       // マルチモーダルモデル用の入力。python の pickle ライブラリ用
│  │  └─fft                            // 何が入ってるか忘れた
│  ├─5s_0.5shift                       // 5sec 関連
│  │  ├─wav　　　　　　　　　　　　　　　 // もとの音源たち
│  │  ├─unknown                        // 未知のもとの音源たち
│  │  │  └─wav
│  │  └─pickles1                       // マルチモーダルモデル用の入力。python の pickle ライブラリ用
├─models                               // 学習済みモデルの保存場所 pytorch だったり keras だったりする。すみません。
└─note　　　　　　　　　　　　　　　　　　// 学会用のデータだったり、一次元特徴量の csv だったり、メモだったりする。
</pre>

# Model

概略図

最終層は Sigmoid ではなくて SoftMax です。

![image](https://user-images.githubusercontent.com/49775901/179500271-435503f8-10ba-4f2a-accf-5855662d2e8b.png)


# Dataset

構造


![image](https://user-images.githubusercontent.com/49775901/179500507-a1cdd45d-edfc-4a2f-bac7-f69480c803da.png)
