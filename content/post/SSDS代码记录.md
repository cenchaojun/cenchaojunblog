+++
title = "SSDS代码记录"

date = 2020-04-13T15:25:51+08:00

categories = ["CV"]
tags = ["学习"]
postauthor = ["cen"]
draft = false

+++

## SSDS代码运行的记录

### 代码连接：<a href="https://github.com/yqyao/SSD_Pytorch" target="_blank">SSDS 代码</a>

* 运行环境需要自己设置一下自己的GPU，要不然容易报错CUDA

  ```python
  os.environ["CUDA_VISIBLE_DEVICES"] = "0"
  ```

---

按照这个教程走就可以了，就没有什么大的问题运行结果

![训练过程](https://github.com/cenchaojun/cenchaojunblog/tree/develop/content/fig/训练过程.png)虽然照着这个教程可以运行了，但是在换backbone的时候，发现自己找不到预训练的网络，而如果不用预训练的网络的时候，loss就容易出现nan值，根本没法训练，就算你调再小的学习率也还是不行的，想自己找原因，但是自己的实力那么菜~~哈哈，还好找到的这个大佬的邮箱，向他发了询问的邮件，大佬说可以代码有将yolov3的预训练，于是乎找了一下，果然在convert_darknet.py里面有的代码，而且也能看懂，但是我找了一下import model里面有yolo，我靠，这没看到呀，咋整~于是乎灵光一闪，想到可能在其他仓库里面，果不其然，在yolov3里面找到这个权重的转换，但是还不知道能不能实现出来~ 所有的仓库都需要执行sh ./make.sh 一下，要不然找不到相关的包。结果是可以运行的，也找到了mobilenetV2的预训练模型。

* 难点：现在mobilenetV3已经出来了，而且出来好久了，确实要实现这个代码了。加油~