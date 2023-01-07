# Convolutional Neural Netwqork

In this document, I will explore CNN (Convolutional Neural Network) primarily in the context of Computer Vision.
Below is an intuitive explanation of how CNNs work.<br>
この文書では、主にコンピュータビジョンの文脈でCNN（Convolutional Neural Network）を探求していきます。
以下では、CNNがどのように機能するかを直感的に説明する。
<br><br>
Yann LeCun et al. (1989) used back-propagation to learn the convolution kernel coefficients directly from images of hand-written numbers. Learning was thus fully automatic, performed better than manual coefficient design, and was suited to a broader range of image recognition problems and image types.
Wei Zhang et al. (1988) used back-propagation to train the convolution kernels of a CNN for alphabets recognition. The model was called Shift-Invariant Artificial Neural Network (SIANN) before the name CNN was coined later in the early 1990s. Wei Zhang et al. also applied the same CNN without the last fully connected layer for medical image object segmentation (1991) and breast cancer detection in mammograms (1994). 
This approach became a foundation of modern computer vision.
<br><br>
Yann LeCunら（1989）は、手書きの数字の画像から直接コンボリューションカーネル係数を学習するために、バックプロパゲーションを使用した。このため、学習は完全に自動化され、手動による係数設計よりも性能が良く、より広範囲の画像認識問題や画像タイプに適していた。
Wei Zhangら（1988）は、アルファベット認識用CNNの畳み込みカーネルをバックプロパゲーションで学習させた。このモデルは、後にCNNという名前が1990年代初頭に作られる以前は、シフト不変人工ニューラルネットワーク（SIANN）と呼ばれていた。Wei Zhangらは、最後の完全連結層を持たない同じCNNを、医療画像の物体分割(1991)やマンモグラムの乳がん検出(1994)にも適用している。
この手法は、現代のコンピュータビジョンの基礎となった。

<img width="500" alt="Screen Shot 2023-01-04 at 1 49 32 AM" src="https://user-images.githubusercontent.com/46320499/210435002-995525e6-00ea-47fc-a262-7091f055da06.png"><br>
<img width="700" alt="Screen Shot 2023-01-04 at 12 59 25 AM" src="https://user-images.githubusercontent.com/46320499/210427722-9816e204-4c62-429d-b177-1e318e03c39e.png"><br>

- **[Basics of CNN](CNNBasics.md)**<br>
- **[Transposed Convolutions](TransposedConvolution.md)**<br>
