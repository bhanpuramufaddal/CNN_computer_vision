## VGG
### VGG Block

A VGG block consists of multiple Convolutional Layers with kernel 3*3 and padding one each accompanied with ReLU Activation. 
Layer with At the end, there is a Max Pool Layer with 2*2 kernel and stride 2.
VGGブロックは、カーネル3*3、パディング1の複数の畳み込み層とReLUアクティベーションで構成されています。
最後に2*2カーネル、ストライド2のMax Pool Layerがある。

<img width="300" alt="Screen Shot 2023-01-17 at 10 46 37 AM" src="https://user-images.githubusercontent.com/46320499/212815824-f2034fa0-349e-45bf-ba90-9e89e99fa36b.png">

```python
import torch
from torch import nn

def vgg_block(num_convs, out_channels):
    layers = []
    for _ in range(num_convs):
        layers.append(nn.LazyConv2d(out_channels, kernel_size=3, padding=1))
        layers.append(nn.ReLU())
    layers.append(nn.MaxPool2d(kernel_size=2,stride=2))
    return nn.Sequential(*layers)
```
### VGG Network
Similar to AlexNet or LeNet, VGG also has Convolutional Layers in the beginning accompanied with A Fully Connected Layer at the end.
But instead of Single CNN Layers, we have VGG Blocks.

AlexNetやLeNetと同様に、VGGも最初に畳み込み層があり、最後に完全連結層があります。
しかし、単一のCNN層ではなく、VGGブロックがあります。

<img width="400" alt="Screen Shot 2023-01-17 at 10 57 27 AM" src="https://user-images.githubusercontent.com/46320499/212817106-50caf9a5-13bf-41d1-b74f-5615021e4474.png">
