# Basics of Convolutional Neural etwork

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

## Calculating Output Dimension
i: input dime <br>
k: kernel size <br>
p: paddingf length <br>
s: stride <br>
o: output dim <br>
<img width="300" alt="Screen Shot 2023-01-07 at 11 27 08 PM" src="https://user-images.githubusercontent.com/46320499/211164089-0a0ccf0b-3a95-4036-b9d3-849ab21b01a3.png"><br><br>

