## Pooling
Pooling is similar to discrete convolutions except that instead element-wise multiplication with the kernel, a different operation is performed called the pooling function. The primary motivation for this is dimensional reduction.

It is analogous to a non-linear activation function like Sigmoid or ReLU in fully connected network.

There are 2 popular pooling operations, Average Pooling and Max Pooling.<br>
プーリングは離散畳み込みと似ているが、カーネルとの要素ごとの乗算の代わりに、プーリング関数という別の演算が行われる。その主な動機は次元の削減である。
プーリングには、

これは、完全連結ネットワークにおけるシグモイドやReLUのような非線形活性化関数に類似している。

Average Pooling と Max Pooling の2つがある。

### Average Pooling
Take an average of all elements in the kernel. <br>
カーネル内の全要素の平均をとる。

<img width="500" alt="Screen Shot 2023-01-05 at 8 14 37 AM" src="https://user-images.githubusercontent.com/46320499/210689719-cca0b187-1bca-4a2a-b29a-913cefe5e020.png"><br>

Output values of a 3 × 3 average pooling operation on a 5 × 5 input using 1 × 1 strides.

### Max Pooling
Take the maximum of all elements in the kernel. <br>
カーネル内の全要素の最大値をとる。

<img width="500" alt="Screen Shot 2023-01-05 at 8 19 18 AM" src="https://user-images.githubusercontent.com/46320499/210690280-d96e1306-fdeb-4fb3-9047-2136e49be3b1.png"><br>

Output values of a 3 × 3 max pooling operation on a 5 × 5 input using 1 × 1 strides.

