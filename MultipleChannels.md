## Multiple Channels
In case where we have multiple channels, or multiple feature maps, then we need multiple kernels to deal with them. 
複数のチャンネル、あるいは複数の特徴マップがある場合、それらを扱うために複数のカーネルが必要になります。

### Multiple Input Channels with Single Output Channel
Suppose, we have ci input channels, than we can have ci kernels. Now for each kernel we will have one output thus in total ci output channels. 
Now we can  combine these ci channels into one by summing over elementwise.

入力チャンネルがci個、カーネルがci個あるとします。各カーネルには1つの出力があり、合計でCi個の出力チャンネルがあることになります。
さて、これらのci個のチャンネルを、要素ごとに合計することで1つにまとめることができます。

<img width="800" alt="Screen Shot 2023-01-16 at 11 17 20 PM" src="https://user-images.githubusercontent.com/46320499/212739280-969c28d1-0451-44e0-9995-7687b1733150.png">

### Multiple Input Channels and Multiple Output Channels
1. ci input channels, co output channels.
2. For every input channel, we have co kernels, now total output channels is ci * co
3. Now we combine ci *co output channels into co output channels using elemmentwise addition for of ci inputs for every output co.
4. Thus we finally get co outputs.
<br>

1. ci個の入力チャンネル、co個の出力チャンネル。
2. 各入力チャンネルには co 個のカーネルがあり，総出力チャンネルは ci * co となります．
3. ここで，ci * co 出力チャンネルを co 出力チャンネルに結合するために，各出力 co に対して ci 入力のエレメント単位の加算を行います．
4. こうして、最終的にco個の出力が得られます。

<img width="800" alt="Screen Shot 2023-01-16 at 11 54 58 PM" src="https://user-images.githubusercontent.com/46320499/212744789-119d75e5-ed00-4059-8853-99c1fd3ea781.png">
