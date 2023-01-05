# Convolutional Neural Netwqork

In this document, I will explore CNN (Convolutional Neural Network) primarily in the context of Computer Vision.
Below is an intuitive explanation of how CNNs work.<br>
この文書では、主にコンピュータビジョンの文脈でCNN（Convolutional Neural Network）を探求していきます。
以下では、CNNがどのように機能するかを直感的に説明する。

<img width="500" alt="Screen Shot 2023-01-04 at 1 49 32 AM" src="https://user-images.githubusercontent.com/46320499/210435002-995525e6-00ea-47fc-a262-7091f055da06.png"><br>
<img width="700" alt="Screen Shot 2023-01-04 at 12 59 25 AM" src="https://user-images.githubusercontent.com/46320499/210427722-9816e204-4c62-429d-b177-1e318e03c39e.png"><br>

## Strides
Strides is the measure of by how many units you translate the kernel between 2 convolutions.
In most cases, we translate the kernel by a single unit thus stride = 1.
We can also have cases with stride = 2 or more.<br>

ストライドとは、2つのコンボリューションの間でカーネルを何単位で変換するかを示す尺度である。
多くの場合、カーネルは1単位で変換されるので、ストライド=1。
しかし、ストライドが2以上の場合もある。

Example : 5*5 input, 3*3 kernel, stride = 2, padding = 0 <br>
<img width="750" alt="Screen Shot 2023-01-04 at 9 09 45 PM" src="https://user-images.githubusercontent.com/46320499/210592383-105895dd-c738-4a44-9725-9cdf6279b1c6.png"><br>

## Zero Padding
<img width="700" alt="Screen Shot 2023-01-04 at 2 07 45 AM" src="https://user-images.githubusercontent.com/46320499/210437554-978eba0d-f1c2-4ae9-8d01-2eaf38dc2968.png"><br>

There are two primary cases of Zero Padding,<br>
Zero Paddingには、主に2つのケースがあります。
1. Half Padding
2. Full Padding

### Half Padding
When you want to preserve the dimension of the input, you choose a padding length such that the input size and output size are equal. This is referred to as half padding.<br>
入力の寸法を維持したい場合は、入力サイズと出力サイズが等しくなるようなパディング長を選択する。これをハーフパディングという。
Example, Input : 

<img width="700" alt="Screen Shot 2023-01-04 at 12 36 50 PM" src="https://user-images.githubusercontent.com/46320499/210501838-109233a8-37be-48e1-8cfe-02bb9f41c056.png"><br>

### Full Padding
In this configuration, we make sure that even boundary elements have equal representation in the output. <br>
この構成では、境界の要素も均等に出力されるようにします。

<img width="700" alt="Screen Shot 2023-01-04 at 4 32 16 PM" src="https://user-images.githubusercontent.com/46320499/210541386-eb48c4f2-3acb-4fc2-9d8c-bc963b17a543.png"><br>

padding_len = kernel - 1

## Pooling
Pooling is similar to discrete convolutions except that instead element-wise multiplication with the kernel, a different operation is performed called the pooling function. The primary motivation for this is dimensional reduction.
There are 2 popular pooling operations, Average Pooling and Max Pooling.<br>
プーリングは離散畳み込みと似ているが、カーネルとの要素ごとの乗算の代わりに、プーリング関数という別の演算が行われる。その主な動機は次元の削減である。
プーリングには、Average Pooling と Max Pooling の2つがある。

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
