---
layout: post
title: "Pytorch GPU 사용 확인"
date: 2021-01-09
categories: Python
tags: [Pytorch, GPU, Python, AI]
---



# PyTorch가 GPU를 사용하고 있는지 확인

아래 명령어를 통해  PyTorch가  GPU를 사용할 수 있는지 확인한다.





## Preliminaries

```python
# Import PyTorch
import torch
```

## GPU카드가 몇개 있는지 확인

```python
# How many GPUs are there?
print(torch.cuda.device_count())
1
```



## 현재 어떤 GPU카드를 쓰고있는지 확인

```python
# Which GPU Is The Current GPU?
print(torch.cuda.current_device())
0
```



## 현재 GPU의 이름 확인

```python
# Get the name of the current GPU
print(torch.cuda.get_device_name(torch.cuda.current_device()))
GeForce GTX 1080 Ti
```



## PyTorch가 GPU를 사용하는지 확인

```python
# Is PyTorch using a GPU?
print(torch.cuda.is_available())
True
```

#### 