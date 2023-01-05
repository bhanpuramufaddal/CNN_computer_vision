# Convolutional Neural Netwqork

In this document, I will explore CNN (Convolutional Neural Network) primarily in the context of Computer Vision.
Below is an intuitive explanation of how CNNs work.
この文書では、主にコンピュータビジョンの文脈でCNN（Convolutional Neural Network）を探求していきます。
以下では、CNNがどのように機能するかを直感的に説明する。

<img width="500" alt="Screen Shot 2023-01-04 at 1 49 32 AM" src="https://user-images.githubusercontent.com/46320499/210435002-995525e6-00ea-47fc-a262-7091f055da06.png">
<img width="700" alt="Screen Shot 2023-01-04 at 12 59 25 AM" src="https://user-images.githubusercontent.com/46320499/210427722-9816e204-4c62-429d-b177-1e318e03c39e.png">

## Strides
Strides is the measure of by how many units you translate the kernel between 2 convolutions.
In most cases, we translate the kernel by a single unit thus stride = 1.
We can also have cases with stride = 2 or more.

ストライドとは、2つのコンボリューションの間でカーネルを何単位で変換するかを示す尺度である。
多くの場合、カーネルは1単位で変換されるので、ストライド=1。
しかし、ストライドが2以上の場合もある。

Example : 5*5 input, 3*3 kernel, stride = 2, padding = 0 
<img width="750" alt="Screen Shot 2023-01-04 at 9 09 45 PM" src="https://user-images.githubusercontent.com/46320499/210592383-105895dd-c738-4a44-9725-9cdf6279b1c6.png">

## Zero Padding
<img width="700" alt="Screen Shot 2023-01-04 at 2 07 45 AM" src="https://user-images.githubusercontent.com/46320499/210437554-978eba0d-f1c2-4ae9-8d01-2eaf38dc2968.png">

There are two primary cases of Zero Padding,
Zero Paddingには、主に2つのケースがあります。
1. Half Padding
2. Full Padding

### Half Padding
When you want to preserve the dimension of the input, you choose a padding length such that the input size and output size are equal. This is referred to as half padding.
入力の寸法を維持したい場合は、入力サイズと出力サイズが等しくなるようなパディング長を選択する。これをハーフパディングという。
Example, Input : 

<img width="700" alt="Screen Shot 2023-01-04 at 12 36 50 PM" src="https://user-images.githubusercontent.com/46320499/210501838-109233a8-37be-48e1-8cfe-02bb9f41c056.png">

### Full Padding
In this configuration, we make sure that even boundary elements have equal representation in the output.
この構成では、境界の要素も均等に出力されるようにします。

<img width="700" alt="Screen Shot 2023-01-04 at 4 32 16 PM" src="https://user-images.githubusercontent.com/46320499/210541386-eb48c4f2-3acb-4fc2-9d8c-bc963b17a543.png">

padding_len = kernel - 1

