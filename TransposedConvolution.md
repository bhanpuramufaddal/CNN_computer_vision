# Upsampling and Transposed Convolution
Convolution generally reduces the dimension of the image. But in several task such as image reconstruction, Image segmentation or auto-encoders, you need to preserve the output dimension. This can be done in two ways:

1. Perform Half-Padding to preserve dimension at every step of convolution
2. Perform Transpose Convolution to recover dimension of the image from a lower dimension.

We have already discussed Half-Padding in the previous section, Here we will discuss Transpose Convolution.

一般に畳み込みは画像の次元を小さくする。しかし、画像再構成、画像分割、オートエンコーダーなどのタスクでは、出力次元を維持する必要があります。これは2つの方法で行うことができる。

1. Half-Paddingを行い、畳み込みの各ステップで次元を保持する。
2. 低次元から画像の次元を回復するためにTransposed Convolutionを実行する。

Half-Padding については前章で説明しましたが、ここではTransposed Convolution について説明します。

## Nearest Neighbors
In Nearest Neighbours, as the name suggests we take an input pixel value and copy it to the K-Nearest Neighbours where K depends on the expected output.
ニアレストネイバーズでは、その名が示すように、入力されたピクセル値をK-ニアレストネイバーズにコピーします（Kは期待される出力に依存します）。
<img width="500" alt="Screen Shot 2023-01-08 at 1 27 45 AM" src="https://user-images.githubusercontent.com/46320499/211168317-66ed5f0d-6f56-4768-be76-46bbb80894cc.png">

## Bi-Linear Interpolation
<img width="500" alt="Screen Shot 2023-01-08 at 1 28 35 AM" src="https://user-images.githubusercontent.com/46320499/211168438-a334e587-5c20-43be-984e-d427294dc981.png"><br>
Converting 2*2 into 4*4, the spaces in the middle are file by linear interpolation of the values in the 2*2 matrix.<br>
2*2を4*4に変換し、真ん中のスペースは2*2マトリックスの値を線形補間してファイル化したものです。

## Max-Unpooling
1. For every max-pooling layer in the encoding step, make note of all the index of these max values. Let's call this list of set of max value indices <br>
S = [a1,a2 ...] where a1 = {idx1, idx2 ...}, idx : index of max values
2. Then while upsampling fill output matrix with zeros.
3. Now at every index of the max values in S, replace these the values at this index with values from previous layer.
<br>

1. エンコードステップにおけるすべてのマックスプーリングレイヤーについて、これらのマックスバリューのすべてのインデックスをメモしておく。この最大値インデックスのセットをリストと呼ぶことにする <br>
S = [a1,a2 ...] ここで a1 = {idx1, idx2 ...}, idx : 最大値のインデックス
2. 次に、アップサンプリング中に出力行列をゼロで埋めます。
3. ここで、S の最大値のインデックスごとに、このインデックスの値を前の層の値で置き換えます。

<img width="800" alt="Screen Shot 2023-01-08 at 2 12 48 PM" src="https://user-images.githubusercontent.com/46320499/211187682-6d5bd945-5101-49d0-a138-df42bf6e609e.png">

## Transpose Convolution
The simplest way to think about a transposed convolution on a given input is
to imagine such an input as being the result of a direct convolution applied on
some initial feature map. The trasposed convolution can be then considered as
the operation that allows to recover the shape of this initial feature map.

与えられた入力に対する転置畳み込みについて考える最も簡単な方法は次のとおりです。
適用された直接畳み込みの出力などの操作の入力を想像する
いくつかの初期機能マップ。転置畳み込みは、次のように考えることができます。
この初期の特徴マップの形状を復元できる操作。

The major difference between transposed and previous techniques is that in transposed convolution, the kernel is learned and can be improved with training. This will give better results.
転置された手法と以前の手法の主な違いは、転置畳み込みではカーネルが学習され、トレーニングによって改善できることです。これにより、より良い結果が得られます。

Let’s consider the convolution of a 3×3 kernel on a 4×4 input with unitary
stride and no padding (i.e., i = 4, k = 3, s = 1 and p = 0). As depicted in
Figure 2.1, this produces a 2 × 2 output. The transpose of this convolution will
then have an output of shape 4 × 4 when applied on a 2 × 2 input.

4×4入力の3×3カーネルの畳み込みを、ユニタリーストライドとパディング無しで考えてみよう。
パディングなし（すなわち、i = 4, k = 3, s = 1, p = 0）。図2.1に示すように
図2.1に描かれているように、これは2×2の出力を生成する。この畳み込みの転置は
この畳み込みの転置は、2×2の入力に適用すると、4×4の形状の出力となる。

### Algorithm
| Convolution Type | Operation | Zero inserted (z) | Padding | Stride | Output Size
| --- | --- | --- | --- | --- | --- | 
| Standard | Downsampling | z = 0 | p | s | (i + 2*p - k)/s + 1 |
| Transposed | Upsampling | z = s - 1 | p` = k - p - 1| s` = 1 | o` = (i - 1)*s + k - 2*p |

1. Calculate new parameters z and p’
2. Between each row and columns of the input, insert z number of zeros. This increases the size of the input to (2*i-1)x(2*i-1)
3. Pad the modified input image with p’ number of zeros
4. Carry out standard convolution on the image generated from step 3 with a stride length of 1

<br>
1. 新しいパラメータzとp'を計算する。
2. 入力の各行と各列の間に、z 個の 0 を挿入する。これにより、入力のサイズは (2*i-1)x(2*i-1) に増加する。
3. 修正された入力画像に p' 個のゼロを詰める。
4. ステップ 3 で生成された画像に対して，ストライド長 1 で標準的な畳み込みを行う。
<br>
<img width="1000" alt="Screen Shot 2023-01-09 at 4 00 43 PM" src="https://user-images.githubusercontent.com/46320499/211288074-8cbc281a-060d-41b9-abe6-4eada22ca75d.png">


