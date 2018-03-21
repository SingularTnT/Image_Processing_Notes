# image-processing-note
some notes or tricks on image processing

## Python
1. RGB转灰度
```
import numpy as np
image = np.mean(image, axis=2)
```

## C++

## Matlab


## Caffe2
方法1:使用workspace.RunNetOnce,初始化网络，运行网络，然后销毁网络。
```
workspace.RunNetOnce(net)
```

方法2:先使用workspace.CreateNet初始化网络，然后使用workspace.RunNet来运行网络
```
workspace.CreateNet(net)
workspace.RunNet(net.Proto().name)
```


RunNetOnce用来运行生成权值和数据的网络，常用于初始化，这样的网络一次生成完，权值输出或数据就存在当前的workspace中，网络本身就没有存在的必要了，就直接销毁，而RunNet可以用来重复训练网络，一开始使用CreateNet，不断迭代调用RunNet就可以不断运行网络更新参数了
