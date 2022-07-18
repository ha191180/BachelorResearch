<div align="center"></div>
<div align="center">
<img src="https://user-images.githubusercontent.com/49775901/177437930-5b03d608-56fb-4349-afb3-006e06ae7d4a.gif">
<img src="https://user-images.githubusercontent.com/49775901/177435525-71c41541-4b9a-4ae3-8e6a-996372167f56.png" height=93>
<img src="https://user-images.githubusercontent.com/49775901/177437930-5b03d608-56fb-4349-afb3-006e06ae7d4a.gif"></div>

# Description

深層学習を用いて音楽の感情認識を行います。

# Files

<pre>
├─util
│  └─visualization_for_docs
├─src                                  // データセット生成とモデルの学習関係
│  ├─my_model                          // マルチモーダルなモデル
│  ├─train_melspec                     // 特徴量にSTFTを用いるモデル
│  ├─train_stft
│  │  ├─train_efficient_net_v2
│  │  ├─train_mnist
│  │  └─train_VGG16_configured
│  ├─train_1d_data
│  ├─train_logmelspec
│  └─make_datasets
│      └─stft
├─trash
├─MER_audio_taffc_dataset_wav
│  ├─Q1
│  ├─Q2
│  ├─Q3
│  ├─Q4
│  ├─renamed
│  ├─2s
│  │  ├─stft_crop_0.2
│  │  ├─stft_crop_0.1
│  │  ├─stft_img
│  │  ├─Q3
│  │  ├─Q1
│  │  ├─Q2
│  │  ├─Q4
│  │  ├─stft_crop_0.15
│  │  ├─unknown
│  │  ├─unknown_img
│  │  ├─melspectro_img
│  │  ├─unknown_spectro
│  │  ├─log-melspectro_img
│  │  ├─pickles1
│  │  └─fft
│  ├─5s_0.5shift
│  │  ├─wav
│  │  ├─unknown
│  │  │  └─wav
│  │  └─pickles1
├─models
└─note

</pre>

