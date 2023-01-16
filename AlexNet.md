## AlexNet
AlexNet, which employed an 8-layer CNN, won the ImageNet Large Scale Visual Recognition Challenge 2012 by a large margin (Russakovsky et al., 2013). 
The architectures of AlexNet and LeNet are strikingly similar except that AlexNet is much deeper than the comparatively small LeNet5. 
AlexNet consists of eight layers: five convolutional layers, two fully connected hidden layers, and one fully connected output layer. 
Second, AlexNet used the ReLU instead of the sigmoid as its activation function. 

8層CNNを採用したAlexNetは、ImageNet Large Scale Visual Recognition Challenge 2012で大差をつけて優勝した（Russakovsky et al.） 
AlexNetとLeNetのアーキテクチャは、AlexNetが比較的小規模なLeNetよりもはるかに深いことを除けば、驚くほどよく似ています5。
AlexNetは、5つの畳み込み層、2つの完全連結隠れ層、1つの完全連結出力層の8層で構成されています。
第二に、AlexNetは活性化関数としてシグモイドの代わりにReLUを使用しています。

By replacing Sigmoid with ReLU, SigmoidをReLUに置き換えることにより。
1. Computatiobnally ReLU is cheaper than Sigmoid
2. ReLU activation function makes model training easier when using different parameter initialization methods. 
This is because, when the output of the sigmoid activation function is very close to 0 or 1, the gradient of these regions is almost 0, 
so that backpropagation cannot continue to update some of the model parameters. In contrast, 
the gradient of the ReLU activation function in the positive interval is always 1
<br>

1. ReLUはSigmoidより計算量が少ない。
2. ReLU活性化関数を用いることで、パラメータの初期化方法が異なる場合でも、モデル学習が容易になる。
これは、シグモイド活性化関数の出力が0や1に非常に近い場合、これらの領域の勾配はほぼ0になるからです。
となり、バックプロパゲーションがモデルパラメータの更新を継続できなくなるためである。これに対して 
ReLU活性化関数の勾配は常に1である。
<img width="300" alt="Screen Shot 2023-01-17 at 1 01 45 AM" src="https://user-images.githubusercontent.com/46320499/212753647-4193ad09-6c87-4de0-9f38-88a34206a487.png">
