---
layout: post
title: "데이터 시각화의 기본"
date: 2021-01-01
categories: Data_science
tags: [Data science, Statistics, Visualization]
---



![img](https://wikidocs.net/images/page/92071/matplotlib_logo.PNG)



# 01. Matplotlib 기본 사용



## Pyplot 소개

[matplotlib.pyplot](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.html#module-matplotlib.pyplot) 모듈은 MATLAB과 비슷하게 명령어 스타일로 동작하는 함수의 모음입니다.

pyplot 모듈의 각각의 함수를 사용해서 그래프를 만들고 변화를 줄 수 있습니다.

예를 들어, 그래프 영역을 만들고, 몇 개의 선을 표현하고, 레이블로 꾸미는 등의 일을 할 수 있습니다.



## 기본 그래프

pyplot을 이용해서 어떤 값들을 간단하게 시각화할 수 있습니다.

 

```
import matplotlib.pyplot as plt

plt.plot([1, 2, 3, 4])
plt.ylabel('y-label')
plt.show()
```

**pyplot.plot()** 함수에 하나의 숫자 리스트를 입력함으로써 아래와 같은 그래프가 그려집니다.

Matplotlib은 리스트의 값들이 y 값들이라고 가정하고, x 값 [0, 1, 2, 3]을 자동으로 만들어냅니다.



![img](https://wikidocs.net/images/page/92071/basics_01.png)



plot() 함수는 다양한 기능을 포함하고 있어서, 임의의 개수의 인자를 받을 수 있습니다.

예를 들어, 아래와 같이 입력하면, x와 y 값을 그래프로 나타낼 수 있습니다.

 

```
plt.plot([1, 2, 3, 4], [1, 4, 9, 16])
```



![img](https://wikidocs.net/images/page/92071/basics_02.png)