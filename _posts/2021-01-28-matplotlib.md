---
layout: post
title: "matplotlib"
date: 2021-01-30
categories: Python
tags: [Data science, Python, Visualization, Matplotlib]
---



![img](https://wikidocs.net/images/page/92071/matplotlib_logo.PNG)



[matplotlib.pyplot](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.html#module-matplotlib.pyplot) 모듈은 MATLAB과 비슷하게 명령어 스타일로 동작하는 함수의 모음입니다.

pyplot 모듈의 각각의 함수를 사용해서 그래프를 만들고 변화를 줄 수 있습니다.

예를 들어, 그래프 영역을 만들고, 몇 개의 선을 표현하고, 레이블로 꾸미는 등의 일을 할 수 있습니다.

------



- [Matplotlib x, y 값 입력하기](#matplotlib-x-y-값-입력하기)
- [Matplotlib 마커 지정하기](#matplotlib-마커-지정하기)
  - [**선/마커 표시 형식**](#선마커-표시-형식)
- [Matplotlib 색상 지정하기](#matplotlib-색상-지정하기)
  - [색상 이름 사용하기](#색상-이름-사용하기)
    - [기본 색상](#기본-색상)
    - [CSS 색상](#css-색상)
  - [Hex code 사용하기](#hex-code-사용하기)
- [Matplotlib 그래프 영역 채우기](#matplotlib-그래프-영역-채우기)
  - [두 그래프 사이 영역 채우기](#두-그래프-사이-영역-채우기)
  - [임의의 영역 채우기](#임의의-영역-채우기)
- [Matplotlib 여러 곡선 그리기](#matplotlib-여러-곡선-그리기)
  - [스타일 지정하기](#스타일-지정하기)
- [Matplotlib 그리드 설정하기](#matplotlib-그리드-설정하기)
- [Matplotlib 눈금 표시하기](#matplotlib-눈금-표시하기)
  - [눈금 레이블 지정하기](#눈금-레이블-지정하기)
  - [눈금 스타일 설정하기](#눈금-스타일-설정하기)
- [Matplotlib 타이틀 설정하기](#matplotlib-타이틀-설정하기)
  - [위치와 오프셋 지정하기](#위치와-오프셋-지정하기)
  - [폰트 지정하기](#폰트-지정하기)
- [Matplotlib 수직선/수평선 표시하기](#matplotlib-수직선수평선-표시하기)
- [Matplotlib 막대 그래프 그리기](#matplotlib-막대-그래프-그리기)
  - [스타일 꾸미기](#스타일-꾸미기)
  - [수평 막대 그래프 그리기](#수평-막대-그래프-그리기)
- [Matplotlib 산점도 그리기](#matplotlib-산점도-그리기)
- [Matplotlib 3차원 산점도 그리기](#matplotlib-3차원-산점도-그리기)
- [Matplotlib 히스토그램 그리기](#matplotlib-히스토그램-그리기)
  - [여러 개의 히스토그램 그리기](#여러-개의-히스토그램-그리기)







# 01. Matplotlib x, y 값 입력하기



matplotlib.pyplot 모듈의 **plot()** 함수에 x, y 값을 리스트의 형태로 입력하면

위의 그림과 같은 꺾은선 그래프의 형태로 그래프가 그려집니다.

```
import matplotlib.pyplot as plt

plt.plot([1, 2, 3, 4], [1, 4, 9, 16])
plt.show()
```

두 개의 리스트를 입력하면 순서대로 x, y 값들로 인식합니다.

따라서 (1, 1), (2, 4), (3, 9), (4, 16)를 잇는 그래프가 나타납니다.

결과는 아래와 같습니다.

![img](https://wikidocs.net/images/page/92080/basic_plot2_01.png)







matplotlib.pyplot 모듈의 **xlabel()**, **ylabel()** 함수를 사용하면 그래프의 x, y 축에 대한 레이블을 표시할 수 있습니다.

```
import matplotlib.pyplot as plt

plt.plot([1, 2, 3, 4], [1, 4, 9, 16])
plt.xlabel('X-Label')
plt.ylabel('Y-Label')
plt.show()
```

**xlabel()**, **ylabel()** 함수에 텍스트를 입력해주면, 아래 그림과 같이 각각의 축에 레이블이 표시됩니다.



![img](https://wikidocs.net/images/page/92081/set_label_01.png)![img](https://wikidocs.net/images/page/92081/set_label_00.png)











matplotlib.pyplot 모듈의 **axis()** 함수를 사용하면 x, y 축이 표시되는 범위를 지정할 수 있습니다.

```
import matplotlib.pyplot as plt

plt.plot([1, 2, 3, 4], [1, 4, 9, 16])
plt.xlabel('X-Label')
plt.ylabel('Y-Label')
plt.axis([0, 5, 0, 20])
plt.show()
```

**axis()** 함수에 [xmin, xmax, ymin, ymax]의 형태로 x, y 축의 범위를 지정해줍니다.

입력 리스트는 반드시 네 개의 값 (xmin, xmax, ymin, ymax)이 있어야 합니다.

입력값이 없으면 데이터에 맞게 자동으로 범위를 지정합니다.

결과는 아래와 같습니다.

![img](https://wikidocs.net/images/page/92082/axis_range_01.png)![img](https://wikidocs.net/images/page/92082/axis_range_00.png)













# 02. Matplotlib 마커 지정하기

![img](https://wikidocs.net/images/page/92083/set_marker_00.png)



특별한 입력이 없으면 그래프가 실선으로 그려지지만, 위의 그림과 같은 마커 형태의 그래프를 그릴 수 있습니다.

```
import matplotlib.pyplot as plt

plt.plot([1, 2, 3, 4], [1, 4, 9, 16], 'bo')
plt.xlabel('X-Label')
plt.ylabel('Y-Label')
plt.axis([0, 5, 0, 20])
plt.show()
```

**plot()** 함수에 **‘bo’**를 입력해주면 파란색의 원형 마커로 그래프가 표시됩니다.

‘b’는 blue, ‘o’는 circle을 나타내는 문자입니다.

결과는 아래와 같습니다.



![img](https://wikidocs.net/images/page/92083/set_marker_01.png)


## **선/마커 표시 형식**

선/마커 표시 형식에 대한 예시는 아래와 같습니다.



![img](https://wikidocs.net/images/page/92083/set_marker_02.png)







또한 다양한 색깔, 선 종류, 마커 종류는 아래 표에 정리되어 있습니다.



![img](https://wikidocs.net/images/page/92083/set_marker_03.png)







# Matplotlib 색상 지정하기

![img](https://wikidocs.net/images/page/92085/set_color_00.png)



**plot()** 함수에 아래와 같이 입력하면 각각 빨간색, 파란색, 녹색 선의 그래프가 그려집니다.



![img](https://wikidocs.net/images/page/92085/set_color_001.png)





아래와 같이 **color** 키워드 인자를 사용해서 더 다양한 색상의 이름을 지정할 수 있습니다.



![img](https://wikidocs.net/images/page/92085/set_color_002.png)



```
import matplotlib.pyplot as plt

plt.plot([1, 2, 3, 4], [1, 4, 9, 16], color='springgreen')
plt.xlabel('X-Label')
plt.ylabel('Y-Label')
plt.axis([0, 5, 0, 20])
plt.show()
```

**plot()** 함수에 **color=’springgreen’** 과 같이 입력해주면, springgreen에 해당하는 색깔이 지정됩니다.

결과는 아래와 같습니다.



![img](https://wikidocs.net/images/page/92085/set_color_01.png)




## 색상 이름 사용하기

Matplotlib에서 사용할 수 있는 다양한 색상의 이름을 아래에서 확인하세요.



### 기본 색상

![img](https://wikidocs.net/images/page/92085/set_color_02.PNG)



### CSS 색상

![img](https://wikidocs.net/images/page/92085/set_color_03.PNG)







## Hex code 사용하기

**16진수 코드 (Hex code)** 로 더욱 다양한 색상을 지정할 수 있습니다.

이번에는 선의 색상과 함께 마커와 선의 종류까지 모두 지정해 보겠습니다.



![img](https://wikidocs.net/images/page/92085/set_color2_00.png)



**marker** 키워드 인자는 마커의 스타일을 지정합니다.

**linestyle** 키워드 인자는 선의 스타일을 지정합니다.



```
import matplotlib.pyplot as plt

plt.plot([1, 2, 3, 4], [1, 4, 9, 16], color='#e35f62', marker='o', linestyle='--')
plt.xlabel('X-Label')
plt.ylabel('Y-Label')
plt.axis([0, 5, 0, 20])
plt.show()
```

선의 색상은 ‘#e35f62’와 같이 Hex code로, 마커는 원형 (circle), 선의 종류는 대시 (dashed)로 지정했습니다.

결과는 아래와 같습니다.



![img](https://wikidocs.net/images/page/92085/set_color2_01.png)




# Matplotlib 그래프 영역 채우기



![img](https://wikidocs.net/images/page/92086/fill_region_00.png)



그래프의 특정 영역을 색상으로 채워서 강조할 수 있습니다.

matplotlib.pyplot 모듈에서 그래프의 영역을 채우는 아래의 세가지 함수에 대해 소개합니다.

- fill_between()
- fill_betweenx()
- fill()



```
import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y = [1, 4, 9, 16]

plt.plot(x, y)
plt.xlabel('X-Label')
plt.ylabel('Y-Label')
plt.fill_between(x[1:3], y[1:3], alpha=0.5)                   ## fill_between() 사용
# plt.fill_betweenx(y[2:4], x[2:4], color='pink', alpha=0.5)  ## fill_betweenx() 사용

plt.show()
```

**fill_between()** 함수에 x[1:3], y[1:3]를 순서대로 입력하면,

네 점 (x[1], y[1]), (x[2], y[2]), (x[1], 0), (x[2], 0)을 잇는 영역이 채워집니다.



![img](https://wikidocs.net/images/page/92086/fill_region_01.png)








또한 **fill_betweenx()** 함수에 y[2:4], x[2:4]를 순서대로 입력하면,

네 점 (x[2], y[2]), (x[3], y[3]), (0, y[2]), (0, y[3])을 잇는 영역이 채워집니다.



![img](https://wikidocs.net/images/page/92086/fill_region_02.png)









## 두 그래프 사이 영역 채우기

```
import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y1 = [1, 4, 9, 16]
y2 = [1, 2, 4, 8]

plt.plot(x, y1)
plt.plot(x, y2)
plt.xlabel('X-Label')
plt.ylabel('Y-Label')
plt.fill_between(x[1:3], y1[1:3], y2[1:3], color='lightgray', alpha=0.5)

plt.show()
```

두 개의 그래프 커브 사이 영역을 채우기 위해서는 두 개의 y 값 시퀀스 y1, y2를 입력해줍니다.

네 점 (x[1], y[1]), (x[1], y[2]), (x[2], y[1]), (x[2], y[2]) 사이 영역을 채웁니다.

결과는 아래와 같습니다.



![img](https://wikidocs.net/images/page/92086/fill_region_03.png)



## 임의의 영역 채우기



```
import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y1 = [1, 4, 9, 16]
y2 = [1, 2, 4, 8]

plt.plot(x, y1)
plt.plot(x, y2)
plt.xlabel('X-Label')
plt.ylabel('Y-Label')
plt.fill([1.9, 1.9, 3.1, 3.1], [2, 5, 11, 8], color='lightgray', alpha=0.5)

plt.show()
```

**fill()** 함수에 x, y 값의 리스트를 입력해주면,

각 x, y 점들로 정의되는 다각형 영역을 자유롭게 지정해서 채울 수 있습니다.

결과는 아래와 같습니다.



![img](https://wikidocs.net/images/page/92086/fill_region_04.png)









# Matplotlib 여러 곡선 그리기

![img](https://wikidocs.net/images/page/92087/multiple_curves_00.png)



이번에는 여러 개의 곡선을 하나의 그래프에 나타내 보겠습니다.



```
import matplotlib.pyplot as plt
import numpy as np

a = np.arange(0, 2, 0.2)

plt.plot(a, a, 'r--', a, a**2, 'bo', a, a**3, 'g-.')
plt.show()
```

NumPy 어레이 [ 0. 0.2 0.4 0.6 0.8 1. 1.2 1.4 1.6 1.8]를 만들었습니다.

**plot()** 함수에 x 값, y 값, 스타일을 순서대로 세 번씩 입력하면, 세 개의 곡선 (y=x, y=x^2, y=x^3)이 동시에 그려집니다.

‘r–‘은 빨간색 (Red)의 대쉬 (Dashed) 스타일 선,

‘bo’는 파란색 (Blue)의 원형 (Circle) 마커,

‘g-.’은 녹색 (Green)의 대쉬-닷 (Dash-dot) 스타일 선을 의미합니다.

결과는 아래와 같습니다.



![img](https://wikidocs.net/images/page/92087/multiple_curves_01.png)




## 스타일 지정하기



```
import matplotlib.pyplot as plt
import numpy as np

a = np.arange(0, 2, 0.2)

plt.plot(a, a, 'bo')
plt.plot(a, a**2, color='#e35f62', marker='*', linewidth=2)
plt.plot(a, a**3, color='springgreen', marker='^', markersize=9)
plt.show()
```

첫 번째 곡선의 스타일은 ‘bo’로,

두 번째 곡선은 color=’#e35f62’, marker=’*’, linewidth=2로,

세 번째 곡선은 color=’springgreen’, marker=’^’, markersize=9로 각각 설정했습니다.

결과는 아래와 같습니다.



![img](https://wikidocs.net/images/page/92087/multiple_curves2_01.png)






# Matplotlib 그리드 설정하기



![img](https://wikidocs.net/images/page/92088/set_grid_00.png)



데이터의 위치를 더 명확하게 하기 위해 그래프에 **그리드 (Grid, 격자)**를 표시할 수 있습니다.

matplotlib.pyplot 모듈의 **grid()** 함수를 이용해서 그래프에 다양하게 그리드를 설정해 보겠습니다.





```
import matplotlib.pyplot as plt
import numpy as np

a = np.arange(0, 2, 0.2)

plt.plot(a, a, 'bo')
plt.plot(a, a**2, color='#e35f62', marker='*', linewidth=2)
plt.plot(a, a**3, color='springgreen', marker='^', markersize=9)
plt.grid(True)

plt.show()
```

**plt.grid(True)**와 같이 설정하면, 그래프의 x, y축에 대해 그리드가 표시됩니다.





![img](https://wikidocs.net/images/page/92088/set_grid_01.png)









```
import matplotlib.pyplot as plt
import numpy as np

a = np.arange(0, 2, 0.2)

plt.plot(a, a, 'bo')
plt.plot(a, a**2, color='#e35f62', marker='*', linewidth=2)
plt.plot(a, a**3, color='springgreen', marker='^', markersize=9)
plt.grid(True, axis='y')

plt.show()
```

**axis=y**로 설정하면 가로 방향의 그리드만 표시됩니다.

{‘both’, ‘x’, ‘y’} 중 선택할 수 있고 디폴트는 ‘both’입니다.





![img](https://wikidocs.net/images/page/92088/set_grid_02.png)







```
import matplotlib.pyplot as plt
import numpy as np

a = np.arange(0, 2, 0.2)

plt.plot(a, a, 'bo')
plt.plot(a, a**2, color='#e35f62', marker='*', linewidth=2)
plt.plot(a, a**3, color='springgreen', marker='^', markersize=9)
plt.grid(True, axis='y', color='red', alpha=0.5, linestyle='--')

plt.show()
```

**color**, **alpha**, **linestyle** 파마리터를 사용해서 그리드 선의 스타일을 설정했습니다.

또한 **which** 파라미터를 ‘major’, ‘minor’, ‘both’ 등으로 사용하면 주눈금, 보조눈금에 각각 그리드를 표시할 수 있습니다.





![img](https://wikidocs.net/images/page/92088/set_grid_03.png)





# Matplotlib 눈금 표시하기

![img](https://wikidocs.net/images/page/92089/set_ticks_00.png)



**틱 (Tick)**은 **그래프의 축에 간격을 구분하기 위해 표시하는 눈금**입니다.

이번에는 matplotlib.pyplot 모듈의 **xticks()**, **yticks()**, **tick_params()** 함수를 이용해서

그래프에 눈금을 표시하는 방법에 대해 소개합니다.



```
import matplotlib.pyplot as plt
import numpy as np

a = np.arange(0, 2, 0.2)

plt.plot(a, a, 'bo')
plt.plot(a, a**2, color='#e35f62', marker='*', linewidth=2)
plt.plot(a, a**3, color='springgreen', marker='^', markersize=9)
plt.xticks([0, 1, 2])
plt.yticks(np.arange(1, 6))

plt.show()
```

**xticks()**, **yticks()** 함수는 각각 x축, y축에 눈금을 표시합니다.

예제에서와 같이 파이썬 리스트 또는 NumPy 어레이를 입력하면, 해당하는 위치에 눈금과 숫자 레이블이 표시됩니다.





![img](https://wikidocs.net/images/page/92089/set_ticks_01.png)









## 눈금 레이블 지정하기



```
import matplotlib.pyplot as plt
import numpy as np

a = np.arange(0, 2, 0.2)

plt.plot(a, a, 'bo')
plt.plot(a, a**2, color='#e35f62', marker='*', linewidth=2)
plt.plot(a, a**3, color='springgreen', marker='^', markersize=9)
plt.xticks(np.arange(0, 2, 0.2), labels=['Jan', '', 'Feb', '', 'Mar', '', 'May', '', 'June', '', 'July'])
plt.yticks(np.arange(0, 7), ('0', '1GB', '2GB', '3GB', '4GB', '5GB', '6GB'))

plt.show()
```

**labels** 파라미터를 사용하면 눈금 레이블을 명시적으로 지정할 수 있습니다.





![img](https://wikidocs.net/images/page/92089/set_ticks_02.png)









## 눈금 스타일 설정하기



```
import matplotlib.pyplot as plt
import numpy as np

a = np.arange(0, 2, 0.2)

plt.plot(a, a, 'bo')
plt.plot(a, a**2, color='#e35f62', marker='*', linewidth=2)
plt.plot(a, a**3, color='springgreen', marker='^', markersize=9)
plt.xticks(np.arange(0, 2, 0.2), labels=['Jan', '', 'Feb', '', 'Mar', '', 'May', '', 'June', '', 'July'])
plt.yticks(np.arange(0, 7), ('0', '1GB', '2GB', '3GB', '4GB', '5GB', '6GB'))

plt.tick_params(axis='x', direction='in', length=3, pad=6, labelsize=14, labelcolor='green', top=True)
plt.tick_params(axis='y', direction='inout', length=10, pad=15, labelsize=12, width=2, color='r')

plt.show()
```

**tick_params()** 함수를 사용하면 눈금의 스타일을 다양하게 설정할 수 있습니다.

**axis**는 설정이 적용될 축을 지정합니다. {‘x’, ‘y’, ‘both’} 중 선택할 수 있습니다.

**direction**을 ‘in’, ‘out’으로 설정하면 눈금이 안/밖으로 표시됩니다. {‘in’, ‘out’, ‘inout’} 중 선택할 수 있습니다.

**length**는 눈금의 길이를 지정합니다.

**pad**는 눈금과 레이블과의 거리를 지정합니다.

**labelsize**는 레이블의 크기를 지정합니다.

**labelcolor**는 레이블의 색상을 지정합니다.

**top/bottom/left/right**를 **True/False**로 지정하면 눈금이 표시될 위치를 선택할 수 있습니다.

**width**는 눈금의 너비를 지정합니다.

**color**는 눈금의 색상을 지정합니다.





![img](https://wikidocs.net/images/page/92089/set_ticks_03.png)



# Matplotlib 타이틀 설정하기

![img](https://wikidocs.net/images/page/92090/set_title_00.png)



matplotlib.pyplot 모듈의 **title()** 함수를 이용해서 그래프의 타이틀 (title)을 설정할 수 있습니다.

이 페이지에서는 그래프의 타이틀을 표시하고 위치를 조절하는 방법, 그리고 폰트와 스타일을 설정하는 방법에 대해 알아봅니다.



```
import matplotlib.pyplot as plt
import numpy as np

a = np.arange(0, 2, 0.2)

plt.plot(a, a, 'bo')
plt.plot(a, a**2, color='#e35f62', marker='*', linewidth=2)
plt.plot(a, a**3, color='springgreen', marker='^', markersize=9)
plt.grid(True, axis='y', color='gray', alpha=0.5, linestyle='--')
plt.tick_params(axis='both', direction='in', length=3, pad=6, labelsize=14)
plt.title('Sample graph')

plt.show()
```

**title()** 함수를 이용해서 그래프의 타이틀을 ‘Sample graph’로 설정했습니다.

결과는 아래와 같습니다.





![img](https://wikidocs.net/images/page/92090/set_title_01.png)






## 위치와 오프셋 지정하기



```
plt.title('Sample graph', loc='right', pad=20)
```

loc=’right’로 설정하면, 타이틀이 그래프의 오른쪽 위에 나타나게 됩니다.

‘left’, ‘center’, ‘right’로 설정할 수 있으며 디폴트는 ‘center’입니다.

pad=20은 타이틀과 그래프와의 간격 (오프셋)을 포인트 단위로 설정합니다.

결과는 아래와 같습니다.





![img](https://wikidocs.net/images/page/92090/set_title_02.png)












## 폰트 지정하기



```
plt.title('Sample graph', loc='right', pad=20)

title_font = {
    'fontsize': 16,
    'fontweight': 'bold'
}
plt.title('Sample graph', fontdict=title_font, loc='left', pad=20)
```

fontdict에 딕셔너리 형태로 폰트에 대한 설정을 입력할 수 있습니다.

‘fontsize’를 16으로, ‘fontweight’를 ‘bold’로 설정했습니다.

‘fontsize’는 포인트 단위의 숫자를 입력하거나 ‘smaller’, ‘x-large’ 등의 상대적인 설정을 할 수 있습니다.

‘fontweight’에는 ‘normal’, ‘bold’, ‘heavy’, ‘light’, ‘ultrabold’, ‘ultralight’의 설정을 할 수 있습니다.

matplotlib의 텍스트 설정에 대한 내용은 이 링크를 참고하세요.

결과는 아래와 같습니다.





![img](https://wikidocs.net/images/page/92090/set_title_03.png)





# Matplotlib 수직선/수평선 표시하기

![img](https://wikidocs.net/images/page/92094/set_lines_00.png)



그래프의 특정 값에 해당하는 위치에 수직선/수평선을 표시하기 위해서

matplotlib.pyplot 모듈에서는 아래의 네가지 함수를 지원합니다.

- axhline()
- axvline()
- hlines()
- vlines()



```
import matplotlib.pyplot as plt
import numpy as np

a = np.arange(0, 2, 0.2)

plt.plot(a, a, 'bo')
plt.plot(a, a**2, color='#e35f62', marker='*', linewidth=2)
plt.plot(a, a**3, color='springgreen', marker='^', markersize=9)
plt.xticks(np.arange(0, 2, 0.2), labels=['Jan', '', 'Feb', '', 'Mar', '', 'May', '', 'June', '', 'July'])
plt.yticks(np.arange(0, 7), ('0', '1GB', '2GB', '3GB', '4GB', '5GB', '6GB'))

plt.axhline(1, 0, 0.55, color='gray', linestyle='--', linewidth='1')
plt.axvline(1, 0, 0.16, color='lightgray', linestyle=':', linewidth='2')

plt.axhline(5.83, 0, 0.95, color='gray', linestyle='--', linewidth='1')
plt.axvline(1.8, 0, 0.95, color='lightgray', linestyle=':', linewidth='2')

plt.show()
```

**axhline()** 함수의 첫번째 인자는 y 값으로서 수평선의 위치가 됩니다.

두, 세번째 인자는 xmin, xmax 값으로서 0에서 1 사이의 값을 입력합니다.

0은 왼쪽 끝 (y축), 1은 오른쪽 끝을 의미합니다.



**axvline()** 함수의 첫번째 인자는 x 값으로서 수직선의 위치가 됩니다.

두, 세번째 인자는 ymin, ymax 값으로서 0에서 1 사이의 값을 입력합니다.

0은 아래쪽 끝 (x축), 1은 위쪽 끝을 의미합니다.





![img](https://wikidocs.net/images/page/92094/set_lines_01.png)
기본 사용 - axhline/axvline.





```
import matplotlib.pyplot as plt
import numpy as np

a = np.arange(0, 2, 0.2)

plt.plot(a, a, 'bo')
plt.plot(a, a**2, color='#e35f62', marker='*', linewidth=2)
plt.plot(a, a**3, color='springgreen', marker='^', markersize=9)
plt.xticks(np.arange(0, 2, 0.2), labels=['Jan', '', 'Feb', '', 'Mar', '', 'May', '', 'June', '', 'July'])
plt.yticks(np.arange(0, 7), ('0', '1GB', '2GB', '3GB', '4GB', '5GB', '6GB'))

plt.hlines(4, 1, 1.6, colors='pink', linewidth=3)
plt.vlines(1, 1, 4, colors='pink', linewidth=3)

plt.show()
```

**hlines()** 함수에 y, xmin, xmax를 순서대로 입력하면, 점 (xmin, y)에서 점 (xmax, y)를 따라 수평선을 표시합니다.

**vlines()** 함수에 x, ymin, ymax를 순서대로 입력하면, 점 (x, ymin)에서 점 (x, ymax)를 따라 수평선을 표시합니다.

결과는 아래와 같습니다.





![img](https://wikidocs.net/images/page/92094/set_lines_02.png)





# Matplotlib 막대 그래프 그리기

![img](https://wikidocs.net/images/page/92095/bar_graph_00.png)



**막대 그래프 (Bar graph, Bar chart)**는 범주가 있는 데이터 값을 직사각형의 막대로 표현하는 그래프입니다.

Matplotlib에서는 matplotlib.pyplot의 **bar()** 함수를 이용해서 막대 그래프를 간단하게 표현할 수 있습니다.



연도별로 변화하는 값을 갖는 데이터를 막대 그래프로 나타내 보겠습니다.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.arange(3)
years = ['2017', '2018', '2019']
values = [100, 400, 900]

plt.bar(x, values)
plt.xticks(x, years)
plt.show()
```

np.arange는 주어진 범위와 간격에 따라 균일한 값을 갖는 어레이를 생성하는 함수입니다.

years는 x축에 표시될 연도이고, values는 막대 그래프의 높이로 표시될 y 값 입니다.

먼저 **bar()** 함수에 NumPy 어레이 [0, 1, 2]와 y 값에 해당하는 리스트 [100, 400, 900]를 입력해줍니다.

다음, **xticks()**에 x와 years를 입력해주면, x축에 ‘2017’, ‘2018’, ‘2019’가 순서대로 표시됩니다.

결과는 아래와 같습니다.





![img](https://wikidocs.net/images/page/92095/bar_graph_01.png)








## 스타일 꾸미기

이번에는 막대 그래프에서 막대와 테두리의 색, 두께 등 다양한 스타일을 적용해 보겠습니다.



```
import matplotlib.pyplot as plt
import numpy as np

x = np.arange(3)
years = ['2017', '2018', '2019']
values = [100, 400, 900]

plt.bar(x, values, width=0.6, align='edge', color="springgreen",
        edgecolor="gray", linewidth=3, tick_label=years, log=True)
plt.show()
```

**width**는 막대의 너비입니다. 디폴트 값은 0.8이며, 예제에서는 0.6으로 설정했습니다.

**align**은 틱 (tick)과 막대의 위치를 조절합니다. 디폴트 값은 ‘center’인데, ‘edge’로 설정하면 막대의 왼쪽 끝에 x_tick이 표시됩니다.

**color**는 막대의 색을 지정합니다.

**edgecolor**는 막대의 테두리 색을 지정합니다.

**linewidth**는 테두리의 두께를 지정합니다.

**tick_label**을 어레이 형태로 지정하면, 틱에 어레이의 문자열을 순서대로 나타낼 수 있습니다.

**log=True**로 설정하면, y축이 로그 스케일로 표시됩니다.

결과는 아래와 같습니다.



![img](https://wikidocs.net/images/page/92095/bar_graph2_01.png)

## 수평 막대 그래프 그리기

```
import matplotlib.pyplot as plt
import numpy as np

y = np.arange(3)
years = ['2017', '2018', '2019']
values = [100, 400, 900]

plt.barh(y, values, height=-0.6, align='edge', color="springgreen",
        edgecolor="gray", linewidth=3, tick_label=years, log=False)
plt.show()
```

**height**는 막대의 높이입니다. 디폴트는 0.8인데 -0.6으로 설정했습니다.

**align**은 tick과 막대의 위치를 조절합니다. 디폴트는 ‘center’인데 ‘edge’로 설정하면 막대의 아래쪽 끝에 y_tick이 표시됩니다.

예제에서는 **height**를 음수로 지정했기 때문에 막대의 위쪽 끝에 y_tick이 표시됩니다.

**color**는 막대의 색을 지정합니다.

**edgecolor**는 막대의 테두리색을 지정합니다.

**linewidth**는 테두리의 두께를 지정합니다.

**tick_label**을 어레이 형태로 지정해주면, 틱에 어레이의 문자열을 순서대로 나타낼 수 있습니다.

**log=False**로 설정하면, x 축이 선형 스케일로 표시됩니다. 디폴트는 False입니다.

결과는 아래와 같습니다.





![img](https://wikidocs.net/images/page/92096/horizontal_bar_graph_01.png)





# Matplotlib 산점도 그리기

![img](https://wikidocs.net/images/page/92110/scatter_plot_00.png)



**산점도 (scatter plot)**는 두 변수의 상관 관계를 직교 좌표계의 평면에 데이터를 점으로 표현하는 그래프입니다.

matplotlib.pyplot 모듈의 **scatter()** 함수를 이용하면 **산점도**를 그릴 수 있습니다.



```
import matplotlib.pyplot as plt
import numpy as np

np.random.seed(19680801)    # Reproducible random state

N = 50
x = np.random.rand(N)
y = np.random.rand(N)
colors = np.random.rand(N)
area = (30 * np.random.rand(N))**2

plt.scatter(x, y, s=area, c=colors, alpha=0.5)
plt.show()
```





```
np.random.seed(19680801)    # Reproducible random state
```

**np.random.seed()**를 이용해서 난수 생성의 시드를 설정하면, 같은 난수를 재사용할 수 있습니다.

**seed()**에 들어갈 파라미터는 0에서 4294967295 사이의 정수여야 합니다.





```
N = 50
x = np.random.rand(N)
y = np.random.rand(N)
colors = np.random.rand(N)
area = (30 * np.random.rand(N))**2
```

x, y의 위치, 마커의 색 (colors)과 면적 (area)을 무작위로 지정해줍니다.

예를 들어, x는 [0.7003673, 0.74275081, … ,0.23722644, 0.82394557]으로 0~1 범위에서 무작위의 50 개의 값을 갖습니다.





```
plt.scatter(x, y, s=area, c=colors, alpha=0.5)
```

**scatter()**에 x, y 위치를 입력해줍니다.

**s**는 마커의 면적을, **c**는 마커의 색을 지정합니다.

**alpha**는 마커 색의 투명도를 결정합니다.

결과는 아래와 같습니다.



![img](https://wikidocs.net/images/page/92110/scatter_plot_01.png)

# Matplotlib 3차원 산점도 그리기

![img](https://wikidocs.net/images/page/92111/3d_scatter_plot_00.png)



이번에는 **scatter()** 함수를 이용해서 **3차원 산점도 (3D Scatter plot)**를 그려 보겠습니다.

```
from mpl_toolkits.mplot3d import Axes3D
import matplotlib.pyplot as plt
import numpy as np

n = 100
xmin, xmax, ymin, ymax, zmin, zmax = 0, 20, 0, 20, 0, 50
cmin, cmax = 0, 2
xs = np.array([(xmax - xmin) * np.random.random_sample() + xmin for i in range(n)])
ys = np.array([(ymax - ymin) * np.random.random_sample() + ymin for i in range(n)])
zs = np.array([(zmax - zmin) * np.random.random_sample() + zmin for i in range(n)])
color = np.array([(cmax - cmin) * np.random.random_sample() + cmin for i in range(n)])

plt.rcParams["figure.figsize"] = (6, 6)
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
ax.scatter(xs, ys, zs, c=color, marker='o', s=15, cmap='Greens')
plt.show()
```





```
from mpl_toolkits.mplot3d import Axes3D
import matplotlib.pyplot as plt
import numpy as np
```

3차원 그래프를 그리기 위해서 **from mpl_toolkits.mplot3d import Axes3D**를 추가해줍니다.

이 부분은 matplotlib 3.1.0 버전부터는 디폴트로 포함되기 때문에 포함하지 않아도 됩니다.





```
n = 100
xmin, xmax, ymin, ymax, zmin, zmax = 0, 20, 0, 20, 0, 50
cmin, cmax = 0, 2
```

xs, ys는 0에서 20 사이, zs는 0에서 50 사이의 값을 갖도록 범위를 정해줍니다.

color는 0에서 2 사이의 값을 갖는 실수이고, 이 값을 통해 각각 다른 색을 표현합니다.





```
xs = np.array([(xmax - xmin) * np.random.random_sample() + xmin for i in range(n)])
ys = np.array([(ymax - ymin) * np.random.random_sample() + ymin for i in range(n)])
zs = np.array([(zmax - zmin) * np.random.random_sample() + zmin for i in range(n)])
color = np.array([(cmax - cmin) * np.random.random_sample() + cmin for i in range(n)])
```

**np.random.random_sample()**를 통해 각 범위 안에서 임의의 실수를 생성합니다.

이 부분은 아래와 같이 np.random.rand()를 이용해서 동일하게 만들 수 있습니다.

```
xs = (xmax - xmin) * np.random.rand(n) + xmin
ys = (xmax - xmin) * np.random.rand(n) + ymin
zs = (xmax - xmin) * np.random.rand(n) + zmin
color = (xmax - xmin) * np.random.rand(n) + cmin
```





```
plt.rcParams["figure.figsize"] = (6, 6)
```

rcParams를 이용해서 figure의 사이즈를 설정해줍니다.





```
ax = fig.add_subplot(111, projection='3d')
ax.scatter(xs, ys, zs, c=color, marker='o', s=15, cmap='Greens')
```

3D axes를 만들기 위해 **add_subplot()**에 **projection=’3d’**를 입력해줍니다.

**scatter()** 함수에 x, y, z 위치를 어레이의 형태로 입력해줍니다.

**c=color**는 color 어레이의 값들이 색으로 표현되도록 합니다.

마커 (marker)의 형태를 원형 (circle)으로 정해줍니다.

마커의 종류에 대해서는 [마커 지정하기](https://wikidocs.net/92083) 페이지에서 확인하세요.

**cmap=’Greens’**를 통해 colormap을 녹색 계열로 설정합니다.

결과는 아래와 같습니다.



![img](https://wikidocs.net/images/page/92111/3d_scatter_plot_02.png)



# Matplotlib 히스토그램 그리기

![img](https://wikidocs.net/images/page/92112/histogram_00.png)



**히스토그램 (Histogram)**은 **도수분포표를 그래프로 나타낸 것으로서, 가로축은 계급, 세로축은 도수 (횟수나 개수 등)**를 나타냅니다.

계급은 보통 변수의 구간이며 서로 겹치지 않습니다.

matplotlib.pyplot 모듈의 **hist()** 함수를 이용해서 간단한 히스토그램을 그려 보겠습니다.





```
import matplotlib.pyplot as plt

weight = [68, 81, 64, 56, 78, 74, 61, 77, 66, 68, 59, 71, 80, 59, 67, 81, 69, 73, 69, 74, 70, 65]

plt.hist(weight)
plt.show()
```

weight는 몸무게 값을 나타내는 리스트입니다.

**hist()** 함수에 리스트의 형태로 값들을 직접 입력해주면 됩니다.

결과는 아래와 같습니다.



![img](https://wikidocs.net/images/page/92112/histogram_01.png)
히스토그램 그리기.





## 여러 개의 히스토그램 그리기



```
import matplotlib.pyplot as plt
import numpy as np


a = 2.0 * np.random.randn(10000) + 1.0
b = np.random.standard_normal(10000)
c = 20.0 * np.random.rand(5000) - 10.0

plt.hist(a, bins=100, density=True, alpha=0.7, histtype='step')
plt.hist(b, bins=50, density=True, alpha=0.5, histtype='stepfilled')
plt.hist(c, bins=100, density=True, alpha=0.9, histtype='step')
plt.show()
```

Numpy의 **np.random.randn()**, **np.random.standard_normal()**, **np.random.rand()** 함수를 이용해서 임의의 값들을 만들었습니다.

어레이 a는 표준편차 2.0, 평균 1.0을 갖는 정규분포, 어레이 b는 표준정규분포를 따릅니다.

어레이 c는 -10.0에서 10.0 사이의 균일한 분포를 갖는 5000개의 임의의 값입니다.

세 개의 분포를 동시에 그래프에 나타냅니다.

bins는 몇 개의 영역으로 쪼갤지를 설정합니다.

density=True로 설정해주면, 밀도함수가 되어서 막대의 아래 면적이 1이 됩니다.

alpha는 투명도를 의미합니다. 0.0에서 1.0 사이의 값을 갖습니다.

histtype을 ‘step’으로 설정하면 막대 내부가 비어있고, ‘stepfilled’로 설정하면 막대 내부가 채워집니다.

결과는 아래와 같습니다.



![img](https://wikidocs.net/images/page/92112/histogram_02.png)





# Matplotlib 여러 개의 그래프 그리기

**matplotlib.pyplot** 모듈의 **subplot()** 함수를 이용해서 여러 개의 그래프를 하나의 그림으로 나타내는 방법에 대해 소개합니다.

```
import numpy as np
import matplotlib.pyplot as plt

x1 = np.linspace(0.0, 5.0)
x2 = np.linspace(0.0, 2.0)

y1 = np.cos(2 * np.pi * x1) * np.exp(-x1)
y2 = np.cos(2 * np.pi * x2)

plt.subplot(2, 1, 1)                # nrows=2, ncols=1, index=1
plt.plot(x1, y1, 'o-')
plt.title('1st Graph')
plt.ylabel('Damped oscillation')

plt.subplot(2, 1, 2)                # nrows=2, ncols=1, index=2
plt.plot(x2, y2, '.-')
plt.title('2nd Graph')
plt.xlabel('time (s)')
plt.ylabel('Undamped')

plt.tight_layout()
plt.show()
```

우선 [NumPy 함수](https://codetorial.net/numpy/functions/index.html)를 사용해서 두 개의 cosine 함수 y1, y2를 만듭니다.

**subplot(nrows, ncols, index)**의 순서대로 nrows=2, ncols=1을 입력하고,

y1 함수는 index=1, y2 함수는 index=2를 입력해서 각각 위, 아래에 위치하도록 합니다.

결과는 아래와 같습니다.

[![Matplotlib 여러 개의 그래프 그리기 - 기본 사용](https://codetorial.net/matplotlib/_images/subplot_ex01_01.png)](https://codetorial.net/matplotlib/_images/subplot_ex01_01.png)



```
import numpy as np
import matplotlib.pyplot as plt

x1 = np.linspace(0.0, 5.0)
x2 = np.linspace(0.0, 2.0)

y1 = np.cos(2 * np.pi * x1) * np.exp(-x1)
y2 = np.cos(2 * np.pi * x2)

plt.subplot(1, 2, 1)                # nrows=1, ncols=2, index=1
plt.plot(x1, y1, 'o-')
plt.title('1st Graph')
plt.xlabel('time (s)')
plt.ylabel('Damped oscillation')

plt.subplot(1, 2, 2)                # nrows=1, ncols=2, index=2
plt.plot(x2, y2, '.-')
plt.title('2nd Graph')
plt.xlabel('time (s)')
plt.ylabel('Undamped')

plt.tight_layout()
plt.show()
```

두 그래프를 수평 방향으로 배치하기 위해서 **subplot(nrows, ncols, index)**의 순서대로 nrows=1, ncols=2을 입력하고,

y1 함수는 index=1, y2 함수는 index=2를 입력해서 각각 좌우로 위치하도록 합니다.

결과는 아래와 같습니다.

[![Matplotlib 여러 개의 그래프 그리기 - 기본 사용2](https://codetorial.net/matplotlib/_images/subplot_ex01_02.png)](https://codetorial.net/matplotlib/_images/subplot_ex01_02.png)





## Matplotlib 컬러맵 설정하기

[
![Matplotlib 컬러맵 설정하기](https://codetorial.net/matplotlib/_images/set_colormap_00.png)](https://codetorial.net/matplotlib/_images/set_colormap_00.png)

**matplotlib.pyplot** 모듈은 컬러맵을 간편하게 설정하기 위한 여러 함수를 제공합니다.

아래의 함수들을 사용해서 그래프의 컬러맵을 설정하는 방식에 대해 소개합니다.

**autumn()**, **bone()**, **cool()**, **copper()**, **flag()**, **gray()**, **hot()**, **hsv()**, **inferno()**, **jet()**, **magma()**, **nipy_spectral()**,

**pink()**, **plasma()**, **prism()**, **spring()**, **summer()**, **viridis()**, **winter()**.

### 

```
import matplotlib.pyplot as plt
import numpy as np

np.random.seed(0)
arr = np.random.standard_normal((8, 100))

plt.subplot(2, 2, 1)
# plt.scatter(arr[0], arr[1], c=arr[1], cmap='spring')
plt.scatter(arr[0], arr[1], c=arr[1])
plt.spring()
plt.title('spring')

plt.subplot(2, 2, 2)
plt.scatter(arr[2], arr[3], c=arr[3])
plt.summer()
plt.title('summer')

plt.subplot(2, 2, 3)
plt.scatter(arr[4], arr[5], c=arr[5])
plt.autumn()
plt.title('autumn')

plt.subplot(2, 2, 4)
plt.scatter(arr[6], arr[7], c=arr[7])
plt.winter()
plt.title('winter')

plt.tight_layout()
plt.show()
```

[subplot()](https://codetorial.net/matplotlib/subplot_ex01.html) 함수를 이용해서 네 영역에 각각의 그래프를 나타내고,

**spring()**, **summer()**, **autumn()**, **winter()** 함수를 이용해서 컬러맵을 다르게 설정했습니다.

결과는 아래와 같습니다.

[![Matplotlib 컬러맵 설정하기 - 기본 사용](https://codetorial.net/matplotlib/_images/set_colormap_01.png)](https://codetorial.net/matplotlib/_images/set_colormap_01.png)

Matplotlib 컬러맵 설정하기 - 기본 사용

## 컬러바 나타내기

```python
import matplotlib.pyplot as plt
import numpy as np

np.random.seed(0)
arr = np.random.standard_normal((8, 100))

plt.subplot(2, 2, 1)
plt.scatter(arr[0], arr[1], c=arr[1])
plt.viridis()
plt.title('viridis')
plt.colorbar()

plt.subplot(2, 2, 2)
plt.scatter(arr[2], arr[3], c=arr[3])
plt.plasma()
plt.title('plasma')
plt.colorbar()

plt.subplot(2, 2, 3)
plt.scatter(arr[4], arr[5], c=arr[5])
plt.jet()
plt.title('jet')
plt.colorbar()

plt.subplot(2, 2, 4)
plt.scatter(arr[6], arr[7], c=arr[7])
plt.nipy_spectral()
plt.title('nipy_spectral')
plt.colorbar()

plt.tight_layout()
plt.show()
```

**colorbar()** 함수를 사용하면 그래프 영역에 컬러바를 포함할 수 있습니다.

결과는 아래와 같습니다.

[![Matplotlib 컬러맵 설정하기 - 컬러바 나타내기](https://codetorial.net/matplotlib/_images/set_colormap_02.png)](https://codetorial.net/matplotlib/_images/set_colormap_02.png)

Matplotlib 컬러맵 설정하기 - 컬러바 나타내기

## 컬러맵 종류

pyplot 모듈의 **colormaps()** 함수를 사용해서 Matplotlib에서 사용할 수 있는 모든 컬러맵의 이름을 얻을 수 있습니다.

```
import matplotlib.pyplot as plt
from matplotlib import cm

cmaps = plt.colormaps()
for cm in cmaps:
    print(cm)
```

아래 그림은 각 컬러맵의 예시를 나타냅니다.

[![_images/set_colormap_00_1.png](https://codetorial.net/matplotlib/_images/set_colormap_00_1.png)](https://codetorial.net/matplotlib/_images/set_colormap_00_1.png)

# Matplotlib 텍스트 삽입하기

[![Matplotlib 텍스트 삽입하기](https://codetorial.net/matplotlib/_images/addtext00.png)](https://codetorial.net/matplotlib/_images/addtext00.png)



**matplotlib.pyplot** 모듈의 **text()** 함수는 그래프의 적절한 위치에 텍스트를 삽입하도록 합니다.

```
import matplotlib.pyplot as plt
import numpy as np

a = 2.0 * np.random.randn(10000) + 1.0
b = np.random.standard_normal(10000)
c = 20.0 * np.random.rand(5000) - 10.0

font1 = {'family': 'serif',
      'color':  'darkred',
      'weight': 'normal',
      'size': 16}

font2 = {'family': 'Times New Roman',
      'color':  'blue',
      'weight': 'bold',
      'size': 12,
      'alpha': 0.7}

font3 = {'family': 'Arial',
      'color':  'forestgreen',
      'style': 'italic',
      'size': 14}

plt.hist(a, bins=100, density=True, alpha=0.7, histtype='step')
plt.text(1.0, 0.35, 'np.random.randn()', fontdict=font1)
plt.hist(b, bins=50, density=True, alpha=0.5, histtype='stepfilled')
plt.text(2.0, 0.20, 'np.random.standard_normal()', fontdict=font2)
plt.hist(c, bins=100, density=True, alpha=0.9, histtype='step')
plt.text(5.0, 0.08, 'np.random.rand()', fontdict=font3)

plt.show()
```

**text()** 함수를 이용해서 3개의 히스토그램 그래프에 설명을 위한 텍스트를 각각 추가했습니다.

**text()**에 그래프 상의 x 위치, y 위치, 그리고 삽입할 텍스트를 순서대로 입력합니다.

**fontdict** 키워드를 이용하면 font의 종류, 크기, 색상, 투명도, weight 등의 텍스트 스타일을 설정할 수 있습니다.

font1, font2, font3과 같이 미리 지정한 폰트 딕셔너리를 fontdict 키워드에 입력해줍니다.

예제에서는 ‘family’, ‘color’, ‘weight’, ‘size’, ‘alpha’, ‘style’ 등과 같은 텍스트 속성을 사용했습니다.

Matplotlib에서 사용할 수 있는 텍스트 속성들에 대해서는 이 [링크](https://matplotlib.org/3.3.1/tutorials/text/text_props.html)를 참고하세요.

결과는 아래와 같습니다.

[![Matplotlib 텍스트 삽입하기 - 텍스트 스타일 설정하기](https://codetorial.net/matplotlib/_images/addtext02.png)](https://codetorial.net/matplotlib/_images/addtext02.png)







# Matplotlib 수학적 표현 사용하기

[![Matplotlib 수학적 표현 나타내기](https://codetorial.net/matplotlib/_images/mathematical_expressions_00.png)](https://codetorial.net/matplotlib/_images/mathematical_expressions_00.png)



달러 기호 ($) 사이에 위치하는 TeX 마크업 표현을 통해 Matplotlib에서 수학적 표현을 사용할 수 있습니다.

그래프의 제목, 축 레이블, 그리고 데이터 곡선을 설명하는 텍스트 상자에도 수학적 표현을 사용할 수 있습니다.

## 그리스 문자 (Greek Letter)

Matplotlib에서 문자열에 수학적 표현을 사용하기 위해서 아래와 같이 세가지 표현이 필요합니다.

[![Matplotlib 수학적 표현 나타내기 - 그리스 문자](https://codetorial.net/matplotlib/_images/mathematical_expressions_01.png)](https://codetorial.net/matplotlib/_images/mathematical_expressions_01.png)

- **‘r’은 파이썬 문자열을 raw string으로 표현**하도록 합니다.
- Matplotlib의 수학적 표현은 **두 개의 달러 기호 ($) 사이에 위치**해야 합니다.
- **Tex 마크업 언어** ([참고](https://en.wikibooks.org/wiki/LaTeX/Mathematics))를 사용해서 각각의 수학적 표현과 기호를 사용합니다.

```python
import matplotlib.pyplot as plt

plt.plot([1, 2, 3, 4], [1, 4, 9, 16])
plt.xlabel('X-Label')
plt.ylabel('Y-Label')
plt.text(1, 15, r'$\alpha > \beta$', fontdict={'size': 16})

plt.show()
```

**text()** 함수를 사용해서 그래프의 x=1, y=15 위치에 그리스 문자를 포함하는 문자열을 삽입했습니다.

아래 그림과 같이 그래프에 αα와 ββ가 표시됩니다.

[![Matplotlib 수학적 표현 나타내기 - 그리스 문자](https://codetorial.net/matplotlib/_images/mathematical_expressions_02.png)](https://codetorial.net/matplotlib/_images/mathematical_expressions_02.png)

Matplotlib 수학적 표현 나타내기 - 그리스 문자

그리스 문자를 위한 TeX 기호는 아래의 표를 참고하세요.

**소문자**

| αα \alpha  | ββ \beta  | χχ \chi    | δδ \delta    | ϝϝ \digamma    | ϵϵ \epsilon  |
| ---------- | --------- | ---------- | ------------ | -------------- | ------------ |
| ηη \eta    | γγ \gamma | ιι \iota   | κκ \kappa    | λλ \lambda     | μμ \mu       |
| νν \nu     | ωω \omega | ϕϕ \phi    | ππ \pi       | ψψ \psi        | ρρ \rho      |
| σσ \sigma  | ττ \tau   | θθ \theta  | υυ \upsilon  | εε \varepsilon | ϰϰ \varkappa |
| φφ \varphi | ϖϖ \varpi | ϱϱ \varrho | ςς \varsigma | ϑϑ \vartheta   | ξξ \xi       |
| ζζ \zeta   |           |            |              |                |              |

**대문자**

| ΔΔ \Delta | ΓΓ \Gamma | ΛΛ \Lambda | ΩΩ \Omega   | ΦΦ \Phi | ΠΠ \Pi  |
| --------- | --------- | ---------- | ----------- | ------- | ------- |
| ΨΨ \Psi   | ΣΣ \Sigma | ΘΘ \Theta  | ΥΥ \Upsilon | ΞΞ \Xi  | ℧℧ \mho |
| ∇∇ \nabla |           |            |             |         |         |

## 위 첨자 (Superscripts), 아래 첨자 (Subscripts)

위 첨자와 아래 첨자를 위해서는 아래와 같이 각각 ‘^’와 ‘_’ 기호를 사용합니다.

[![Matplotlib 수학적 표현 나타내기 - 위 첨자 (Superscripts), 아래 첨자 (Subscripts)](https://codetorial.net/matplotlib/_images/mathematical_expressions_03.png)](https://codetorial.net/matplotlib/_images/mathematical_expressions_03.png)

### 예제

```
import matplotlib.pyplot as plt

plt.plot([1, 2, 3, 4], [1, 4, 9, 16])
plt.xlabel('X-Label')
plt.ylabel('Y-Label')
plt.text(1, 15, r'$\alpha^2 > \beta_5$', fontdict={'size': 16})

plt.show()
```

‘^’와 ‘_’를 사용해서 그래프에 위 첨자와 아래 첨자를 포함하는 수식 표현을 삽입했습니다.

결과는 아래와 같습니다.

[![Matplotlib 수학적 표현 나타내기 - 위 첨자 (Superscripts), 아래 첨자 (Subscripts)](https://codetorial.net/matplotlib/_images/mathematical_expressions_04.png)](https://codetorial.net/matplotlib/_images/mathematical_expressions_04.png)

Matplotlib 수학적 표현 나타내기 - 위 첨자 (Superscripts), 아래 첨자 (Subscripts)

## 분수 (Fractions)

분수 표현을 사용하기 위해서는 아래와 같이 \frac{ }{ } 표현을 사용합니다.

[![Matplotlib 수학적 표현 나타내기 - 분수 (Fractions)](https://codetorial.net/matplotlib/_images/mathematical_expressions_05.png)](https://codetorial.net/matplotlib/_images/mathematical_expressions_05.png)



```
import matplotlib.pyplot as plt

plt.plot([1, 2, 3, 4], [1, 4, 9, 16])
plt.xlabel('X-Label')
plt.ylabel('Y-Label')
plt.text(1, 15, r'$\frac{1}{2} + \frac{3}{4} = \frac{5}{4}$', fontdict={'size': 16})

plt.show()
```

아래와 같이 그래프에 분수 표현 수식이 삽입되었습니다.

[![Matplotlib 수학적 표현 나타내기 - 분수 (Fractions)](https://codetorial.net/matplotlib/_images/mathematical_expressions_06.png)](https://codetorial.net/matplotlib/_images/mathematical_expressions_06.png)

## 표준 함수 (Standard Functions)와 대형 기호 (Big Symbols)

아래 그림과 같이 Matplotlib에서 삼각함수 (sin, cos, tan 등), 극한 (lim), 최대 (max), 최소 (min) 등의 표현과

다양한 대형 연산자 기호를 사용할 수 있습니다.

[![Matplotlib 수학적 표현 나타내기 - 표준 함수 (Standard Functions)와 대형 기호 (Big Symbols)](https://codetorial.net/matplotlib/_images/mathematical_expressions_11.png)](https://codetorial.net/matplotlib/_images/mathematical_expressions_11.png)

```
import matplotlib.pyplot as plt

plt.plot([1, 2, 3, 4], [1, 4, 9, 16])
plt.xlabel('X-Label')
plt.ylabel('Y-Label')
plt.text(1, 15, r'$\sin (x) \ \cos (x) \ \tan (x)$', fontdict={'size': 16})
plt.text(1, 12, r'$\lim_{x\rightarrow 2} (x^2 - x + 2)$', fontdict={'size': 16})
plt.text(1, 8, r'$\sum_{n=0}^{10}{(n^2 + n)}$', fontdict={'size': 16})
plt.show()
```

그래프에 여러가지 삼각함수와 극한 기호, 그리고 합 기호 (Summation symbol)를 표시했습니다.

결과는 아래와 같습니다.

[![Matplotlib 수학적 표현 나타내기 - 표준 함수 (Standard Functions)와 대형 기호 (Big Symbols)](https://codetorial.net/matplotlib/_images/mathematical_expressions_12.png)](https://codetorial.net/matplotlib/_images/mathematical_expressions_12.png)

Matplotlib 수학적 표현 나타내기 - 표준 함수 (Standard Functions)와 대형 기호 (Big Symbols)

더 다양한 표준 함수의 기호는 아래의 표를 참고하세요.

| Command | Result         | Command | Result         | Command | Result       | Command | Result       |
| :------ | :------------- | :------ | :------------- | :------ | :----------- | :------ | :----------- |
| \Pr     | PrPr           | \arccos | arccosarccos   | \arcsin | arcsinarcsin | \arctan | arctanarctan |
| \arg    | argarg         | \cos    | coscos         | \cosh   | coshcosh     | \cot    | cotcot       |
| \coth   | cothcoth       | \csc    | csccsc         | \deg    | degdeg       | \det    | detdet       |
| \dim    | dimdim         | \exp    | expexp         | \gcd    | gcdgcd       | \hom    | homhom       |
| \inf    | infinf         | \ker    | kerker         | \lg     | lglg         | \lim    | limlim       |
| \liminf | lim inflim inf | \limsup | lim suplim sup | \ln     | lnln         | \log    | loglog       |
| \max    | maxmax         | \min    | minmin         | \sec    | secsec       | \sin    | sinsin       |
| \sinh   | sinhsinh       | \sup    | supsup         | \tan    | tantan       | \tanh   | tanhtanh     |

대형 기호는 아래의 표를 참고하세요.

| Command    | Result | Command   | Result | Command  | Result | Command   | Result |
| :--------- | :----- | :-------- | :----- | :------- | :----- | :-------- | :----- |
| \bigcap    | ⋂⋂     | \bigcup   | ⋃⋃     | \bigodot | ⨀⨀     | \bigoplus | ⨁⨁     |
| \bigotimes | ⨂⨂     | \biguplus | ⨄⨄     | \bigvee  | ⋁⋁     | \bigwedge | ⋀⋀     |
| \coprod    | ∐∐     | \int      | ∫∫     | \oint    | ∮∮     | \prod     | ∏∏     |
| \sum       | ∑∑     |           |        |          |        |           |        |

그리고 더 다양한 수학적 표현의 사용과 그 설명에 대해서는 공식 문서의 설명 ([링크](https://matplotlib.org/3.1.1/tutorials/text/mathtext.html))을 참고하세요.





# Matplotlib 이미지 저장하기

[![Matplotlib 이미지 저장하기](https://codetorial.net/matplotlib/_images/savefig_00.png)](https://codetorial.net/matplotlib/_images/savefig_00.png)



**matplotlib.pyplot** 모듈의 **savefig()** 함수를 사용해서 그래프를 이미지 파일 등으로 저장하는 방법을 소개합니다.

```
import numpy as np
import matplotlib.pyplot as plt

x1 = np.linspace(0.0, 5.0)
x2 = np.linspace(0.0, 2.0)

y1 = np.cos(2 * np.pi * x1) * np.exp(-x1)
y2 = np.cos(2 * np.pi * x2)

plt.subplot(2, 1, 1)                # nrows=2, ncols=1, index=1
plt.plot(x1, y1, 'o-')
plt.title('1st Graph')
plt.ylabel('Damped oscillation')

plt.subplot(2, 1, 2)                # nrows=2, ncols=1, index=2
plt.plot(x2, y2, '.-')
plt.title('2nd Graph')
plt.xlabel('time (s)')
plt.ylabel('Undamped')

plt.tight_layout()
# plt.show()
plt.savefig('savefig_default.png')
```

**savefig()** 함수에 파일 이름을 입력해주면 아래와 같은 이미지 파일이 저장됩니다.

[![Matplotlib 이미지 저장하기 - 기본 사용](https://codetorial.net/matplotlib/_images/savefig_default.png)](https://codetorial.net/matplotlib/_images/savefig_default.png)

Matplotlib 이미지 저장하기 - 기본 사용

## dpi 설정하기

```
plt.savefig('savefig_default.png')
plt.savefig('savefig_50dpi.png', dpi=50)
plt.savefig('savefig_200dpi.png', dpi=200)
```

**dpi (Dots per Inch)**는 이미지의 해상도를 설정합니다. 디폴트는 dpi=100입니다.

해상도에 따라 아래와 같은 이미지가 저장됩니다.

[![Matplotlib 이미지 저장하기 - dpi 설정하기](https://codetorial.net/matplotlib/_images/savefig_dpi.png)](https://codetorial.net/matplotlib/_images/savefig_dpi.png)

Matplotlib 이미지 저장하기 - dpi 설정하기

## facecolor 설정하기

```
plt.savefig('savefig_facecolor.png', facecolor='#eeeeee')
```

**facecolor**는 이미지의 배경색을 설정합니다.

아래와 같은 이미지가 저장됩니다.

[![Matplotlib 이미지 저장하기 - facecolor 설정하기](https://codetorial.net/matplotlib/_images/savefig_facecolor.png)](https://codetorial.net/matplotlib/_images/savefig_facecolor.png)



## bbox_inches 설정하기

```
plt.savefig('savefig_bbox_inches.png', facecolor='#eeeeee')
plt.savefig('savefig_bbox_inches2.png', facecolor='#eeeeee', bbox_inches='tight')
```

**bbox_inches**는 그래프로 저장할 영역을 설정합니다.

디폴트로 **None**이지만, ‘tight’로 지정하면 여백을 최소화하고 그래프 영역만 이미지로 저장합니다.

[![Matplotlib 이미지 저장하기 - bbox_inches 설정하기 (디폴트)](https://codetorial.net/matplotlib/_images/savefig_bbox_inches.png)](https://codetorial.net/matplotlib/_images/savefig_bbox_inches.png)

Matplotlib 이미지 저장하기 - bbox_inches 설정하기 (디폴트)

[![Matplotlib 이미지 저장하기 - bbox_inches 설정하기 (tight)](https://codetorial.net/matplotlib/_images/savefig_bbox_inches2.png)](https://codetorial.net/matplotlib/_images/savefig_bbox_inches2.png)

Matplotlib 이미지 저장하기 - bbox_inches 설정하기 (tight)



## pad_inches 설정하기

```
plt.savefig('savefig_pad_inches.png', facecolor='#eeeeee',
            bbox_inches='tight', pad_inches=0.3)
plt.savefig('savefig_pad_inches2.png', facecolor='#eeeeee',
            bbox_inches='tight', pad_inches=0.5)
```

**bbox_inches=’tight’**로 지정하면 **pad_inches**를 함께 사용해서 **여백 (Padding)**을 지정할 수 있습니다.

**pad_inches**의 디폴트 값은 0.1이며, 0.3과 0.5로 지정했을 때의 결과는 아래와 같습니다.

[![Matplotlib 이미지 저장하기 - pad_inches 설정하기 (0.3)](https://codetorial.net/matplotlib/_images/savefig_pad_inches.png)](https://codetorial.net/matplotlib/_images/savefig_pad_inches.png)

Matplotlib 이미지 저장하기 - pad_inches 설정하기 (0.3)

[![Matplotlib 이미지 저장하기 - pad_inches 설정하기 (0.5)](https://codetorial.net/matplotlib/_images/savefig_pad_inches2.png)](https://codetorial.net/matplotlib/_images/savefig_pad_inches2.png)







# Matplotlib 객체 지향 인터페이스

지금까지 **matplotlib.pyplot** 모듈의 다양한 함수들을 이용해서 간편하게 그래프를 그렸습니다.

Matplotlib는 그래프를 다루는 두 가지의 인터페이스를 제공하는데 첫번째는 **MATLAB 스타일로 pyplot** 모듈을 사용하는 방식이고, 두번째는 **객체 지향 인터페이스**입니다.

Matplotlib 공식 문서에 의하면 더욱 커스터마이즈된 그래프를 표현하기 위해 객체 지향 인터페이스를 사용하기를 권장합니다.



## plt.subplots() 사용하기

pyplot 모듈은 **subplots()**라는 유용한 함수를 제공합니다. ([matplotlib.pyplot.subplots](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.subplots.html#matplotlib.pyplot.subplots))

보통 아래와 같은 방식으로 사용합니다.

### 

```python
import matplotlib.pyplot as plt

fig, ax = plt.subplots()
plt.show()
```



**subplots()** 함수를 호출하면 figure (fig)과 subplot (ax) 객체를 생성해서 튜플의 형태로 반환합니다.

아래와 같은 그림이 나타납니다.

[![Matplotlib 객체 지향 인터페이스 1 - plt.subplots() 사용하기](https://codetorial.net/matplotlib/_images/oo_interface_01.png)](https://codetorial.net/matplotlib/_images/oo_interface_01.png)

Matplotlib 객체 지향 인터페이스 1 - plt.subplots() 사용하기

위의 예제에서, **fig, ax = plt.subplots()**과 같이 사용하지 않고 아래와 같이 사용할 수도 있습니다.

### 

```
import matplotlib.pyplot as plt

# fig, ax = plt.subplots()
fig = plt.figure()
ax = fig.add_axes([0, 0, 1, 1])

plt.show()
```

plt.figure()는 **Figure 클래스의 인스턴스**를 반환합니다.

Figure 클래스의 인스턴스 fig의 메서드 **add_axes()**는 fig에 axes를 하나 추가합니다.

add_axes([left, bottom, width, height])의 형태로 0에서 1 사이의 값을 입력합니다.

이 페이지의 예제들에서는 plt.subplots()을 사용합니다.



## 행과 열 설정하기 (nrows, ncols)

```
import matplotlib.pyplot as plt

fig, ax = plt.subplots(2, 2)
plt.show()
```

**plt.subplots(nrows, ncols)**의 형태로 행과 열의 개수를 지정할 수 있습니다.

만약 지정하지 않으면 기본적으로 행과 열의 개수는 모두 1입니다.

결과는 아래와 같습니다.

[![Matplotlib 객체 지향 인터페이스 1 - 행과 열 설정하기 (nrows, ncols)](https://codetorial.net/matplotlib/_images/oo_interface_02.png)](https://codetorial.net/matplotlib/_images/oo_interface_02.png)

Matplotlib 객체 지향 인터페이스 1 - 행과 열 설정하기 (nrows, ncols)



## X, Y축 공유하기 (sharex, sharey)

앞의 그림에서 네 개의 그래프 영역은 X, Y축의 범위가 같습니다.

이 경우에 중복해서 표시하지 않도록 X축 또는 Y축을 공유하도록 설정할 수 있습니다.

```
import matplotlib.pyplot as plt

fig, ax = plt.subplots(2, 2, sharex=True, sharey=True)
plt.show()
```

sharex=True, sharey=True로 설정함으로써 아래와 같이 중복된 축을 한번만 표시하도록 했습니다.

sharex, sharey에 True, False 이 외에도 ‘all’, ‘none’, ‘row’, ‘col’ 등을 지정할 수 있습니다.

결과는 아래와 같습니다.

[![Matplotlib 객체 지향 인터페이스 1 - X, Y축 공유하기 (sharex, sharey)](https://codetorial.net/matplotlib/_images/oo_interface_03.png)](https://codetorial.net/matplotlib/_images/oo_interface_03.png)

Matplotlib 객체 지향 인터페이스 1 - X, Y축 공유하기 (sharex, sharey)



## 그래프 그리기

```
import matplotlib.pyplot as plt
import numpy as np

x = np.arange(1, 5)     # [1, 2, 3, 4]

fig, ax = plt.subplots(2, 2, sharex=True, sharey=True, squeeze=True)
ax[0][0].plot(x, np.sqrt(x))      # left-top
ax[0][1].plot(x, x)               # right-top
ax[1][0].plot(x, -x+5)            # left-bottom
ax[1][1].plot(x, np.sqrt(-x+5))   # right-bottom

plt.show()
```

NumPy를 이용해서 x값들을 만들고, 네 개의 그래프 영역에 각각 다른 y값을 그래프로 나타냈습니다.

plt.subplots()이 반환하는 ax는 **Matplotlib의 Axes 클래스의 인스턴스**입니다.

행과 열을 각각 2, 2로 지정했기 때문에 ax는 2×2의 형태를 갖는 NumPy 어레이가 됩니다.

위치에 따라 각각 ax[0][0], ax[0][1], ax[1][0], ax[1][1]과 같이 접근해서 사용할 수 있습니다.

결과는 아래와 같습니다.

[![Matplotlib 객체 지향 인터페이스 2 - 그래프 그리기](https://codetorial.net/matplotlib/_images/oo_interface_04.png)](https://codetorial.net/matplotlib/_images/oo_interface_04.png)

Matplotlib 객체 지향 인터페이스 2 - 그래프 그리기



## 스타일 설정하기

```
import matplotlib.pyplot as plt
import numpy as np

x = np.arange(1, 5)     # [1, 2, 3, 4]

fig, ax = plt.subplots(2, 2, sharex=True, sharey=True, squeeze=True)
ax[0][0].plot(x, np.sqrt(x), 'gray', linewidth=3)
ax[0][1].plot(x, x, 'g^-', markersize=10)
ax[1][0].plot(x, -x+5, 'ro--')
ax[1][1].plot(x, np.sqrt(-x+5), 'b.-.')

plt.show()
```



plot()에 각각의 그래프의 스타일을 커스터마이즈하도록 설정할 수 있습니다.

(자세한 내용은 [마커 지정하기](https://codetorial.net/matplotlib/set_marker.html), [색깔 지정하기](https://codetorial.net/matplotlib/set_color.html), [색깔 지정하기2](https://codetorial.net/set_color2.html) 페이지를 참고하세요.)

결과는 아래와 같습니다.

[![Matplotlib 객체 지향 인터페이스 2 - 스타일 설정하기](https://codetorial.net/matplotlib/_images/oo_interface_05.png)](https://codetorial.net/matplotlib/_images/oo_interface_05.png)

Matplotlib 객체 지향 인터페이스 2 - 스타일 설정하기

## 제목과 범례 표시하기

**set_title()**과 **legend()**를 이용해서 각각의 그래프에 제목과 범례를 설정할 수 있습니다.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.arange(1, 5)     # [1, 2, 3, 4]

fig, ax = plt.subplots(2, 2, sharex=True, sharey=True, squeeze=True)
ax[0][0].plot(x, np.sqrt(x), 'gray', linewidth=3, label='y=np.sqrt(x)')
ax[0][0].set_title('Graph 1')
ax[0][0].legend()
ax[0][1].plot(x, x, 'g^-', markersize=10, label='y=x')
ax[0][1].set_title('Graph 2')
ax[0][1].legend(loc='upper left')
ax[1][0].plot(x, -x+5, 'ro--', label='y=-x+5')
ax[1][0].set_title('Graph 3')
ax[1][0].legend(loc='lower left')
ax[1][1].plot(x, np.sqrt(-x+5), 'b.-.', label='y=np.sqrt(-x+5)')
ax[1][1].set_title('Graph 4')
ax[1][1].legend(loc='upper center')

plt.show()
```

**set_title()**은 입력한 문자열을 그래프의 제목으로 나타냅니다.

**legend()**는 **plot()**에서 label을 이용해서 지정한 문자열을 범례에 나타냅니다.

그래프 영역에서 범례가 표시될 위치를 지정할 수 있는데, 지정하지 않으면 최적의 위치에 범례를 표시합니다.

범례가 표시될 위치를 설정하기 위한 옵션은 아래와 같습니다.

```
'best'
'upper right'
'upper left'
'lower left'
'lower right'
'right'
'center left'
'center right'
'lower center'
'upper center'
'center'
```



결과는 아래와 같습니다.

[![Matplotlib 객체 지향 인터페이스 2 - 제목과 범례 표시하기](https://codetorial.net/matplotlib/_images/oo_interface_06.png)](https://codetorial.net/matplotlib/_images/oo_interface_06.png)

Matplotlib 객체 지향 인터페이스 2 - 제목과 범례 표시하기





# Matplotlib 두 종류의 그래프 그리기

```
import matplotlib.pyplot as plt
import numpy as np

# 1. 기본 스타일 설정
plt.style.use('default')
plt.rcParams['figure.figsize'] = (4, 3)
plt.rcParams['font.size'] = 12

# 2. 데이터 준비
x = np.arange(2020, 2027)
y1 = np.array([1, 3, 7, 5, 9, 7, 14])
y2 = np.array([1, 3, 5, 7, 9, 11, 13])

# 3. 그래프 그리기
fig, ax1 = plt.subplots()

ax1.plot(x, y1, '-s', color='green', markersize=7, linewidth=5, alpha=0.7, label='Price')
ax1.set_ylim(0, 18)
ax1.set_xlabel('Year')
ax1.set_ylabel('Price ($)')
ax1.tick_params(axis='both', direction='in')

ax2 = ax1.twinx()
ax2.bar(x, y2, color='deeppink', label='Demand', alpha=0.7, width=0.7)
ax2.set_ylim(0, 18)
ax2.set_ylabel(r'Demand ($\times10^6$)')
ax2.tick_params(axis='y', direction='in')

plt.show()
```



우선 **ax1.twinx()**로 X축을 공유하는 이중 Y축을 만들고,

**ax1.plot()**과 **ax2.bar()**를 사용해서 y1, y2 데이터를 각각 꺾은선 그래프와 막대 그래프의 형태로 나타냈습니다.

(두번째 Y축의 레이블에 표현한 수학적 표현의 사용에 대해서는 [링크](https://codetorial.net/matplotlib/mathematical_expressions.html)를 참고하세요.)

결과는 아래와 같습니다.

[![Matplotlib 두 종류의 그래프 그리기 - 기본 사용](https://codetorial.net/matplotlib/_images/two_types_of_graphs_01.png)](https://codetorial.net/matplotlib/_images/two_types_of_graphs_01.png)



## 그래프 순서 지정하기

위의 그림을 보면 녹색의 꺾은선 그래프가 막대의 뒤에 그려져 있어서 잘 보이지 않습니다.

아래 예제에서는 **set_zorder()** 메서드를 사용해서 그래프가 표시될 순서를 지정해 보겠습니다.

### 

```
import matplotlib.pyplot as plt
import numpy as np

# 1. 기본 스타일 설정
plt.style.use('default')
plt.rcParams['figure.figsize'] = (4, 3)
plt.rcParams['font.size'] = 12

# 2. 데이터 준비
x = np.arange(2020, 2027)
y1 = np.array([1, 3, 7, 5, 9, 7, 14])
y2 = np.array([1, 3, 5, 7, 9, 11, 13])

# 3. 그래프 그리기
fig, ax1 = plt.subplots()

ax1.plot(x, y1, '-s', color='green', markersize=7, linewidth=5, alpha=0.7, label='Price')
ax1.set_ylim(0, 18)
ax1.set_xlabel('Year')
ax1.set_ylabel('Price ($)')
ax1.tick_params(axis='both', direction='in')

ax2 = ax1.twinx()
ax2.bar(x, y2, color='deeppink', label='Demand', alpha=0.7, width=0.7)
ax2.set_ylim(0, 18)
ax2.set_ylabel(r'Demand ($\times10^6$)')
ax2.tick_params(axis='y', direction='in')

ax1.set_zorder(ax2.get_zorder() + 10)
ax1.patch.set_visible(False)

ax1.legend(loc='upper left')
ax2.legend(loc='upper right')

plt.show()
```

**set_zorder()** 메서드는 z-축 방향의 순서를 지정합니다.

아래 그림과 같이 **zorder**가 낮을수록 먼저 그려지고, **zorder**가 높을수록 나중에 그려집니다.

[![Matplotlib 두 종류의 그래프 그리기 - 그래프 순서 지정하기](https://codetorial.net/matplotlib/_images/two_types_of_graphs_02.png)](https://codetorial.net/matplotlib/_images/two_types_of_graphs_02.png)

우선 **ax2.get_zorder()** 메서드를 사용해서 **ax2**의 **zorder**를 얻고,

**ax2**의 **zorder**보다 큰 값을 **ax1**의 **zorder**로 지정함으로써 그래프가 항상 나중에 그려지도록 설정했습니다.

결과는 아래와 같습니다.

[![Matplotlib 두 종류의 그래프 그리기 - 그래프 순서 지정하기](https://codetorial.net/matplotlib/_images/two_types_of_graphs_03.png)](https://codetorial.net/matplotlib/_images/two_types_of_graphs_03.png)

Matplotlib 두 종류의 그래프 그리기 - 그래프 순서 지정하기







# Matplotlib 애니메이션 사용하기

[![Matplotlib 애니메이션 사용하기](https://codetorial.net/matplotlib/_images/animation_funcanimation_00.gif)](https://codetorial.net/matplotlib/_images/animation_funcanimation_00.gif)



다양한 Matplotlib 그래프를 애니메이션으로 나타내고, 파일로 저장할 수 있습니다.

**matplotlib.animation** 모듈의 **FuncAnimation** 클래스를 사용해서 그래프를 애니메이션으로 표현하는 방법에 대해 소개합니다.

### 

```
import numpy as np
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation

fig, ax = plt.subplots()
ax.set_xlim(0, 2*np.pi)
ax.set_ylim(-1.2, 1.2)

x, y = [], []
line, = plt.plot([], [], 'bo')


def update(frame):
    x.append(frame)
    y.append(np.sin(frame))
    line.set_data(x, y)
    return line,


ani = FuncAnimation(fig, update, frames=np.linspace(0, 2*np.pi, 128))
plt.show()
```



**matplotlib.animation** 모듈의 **FuncAnimation** 클래스는 지정한 함수를 반복적으로 호출함으로써 애니메이션을 생성합니다.

**FuncAnimation** 클래스의 첫번째 인자로 **Figure** 객체를, 두번째 인자로는 프레임마다 반복해서 호출할 함수를 지정합니다.

**frames** 키워드 인자에는 반복 가능한 객체를 입력합니다.

[np.linspace(a, b, n)](https://codetorial.net/numpy/functions/numpy_linspace.html)는 a부터 b 사이를 균일한 간격으로 나누는 숫자 n개를 반환합니다.

**update()** 함수에 **frames**에 제공한 값들이 순서대로 제공되어서 프레임을 구성합니다.

아래와 같은 애니메이션이 나타납니다.

[![Matplotlib 애니메이션 사용하기 - 기본 사용](https://codetorial.net/matplotlib/_images/animation_funcanimation_01.gif)](https://codetorial.net/matplotlib/_images/animation_funcanimation_01.gif)

Matplotlib 애니메이션 사용하기 - 기본 사용



## 프레임 간격 설정하기

### 

```
import numpy as np
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation

fig = plt.figure()
ax = plt.axes(xlim=(0, 4), ylim=(-2, 2))
line, = ax.plot([], [], lw=3)


def animate(i):
  x = np.linspace(0, 4, 1000)
  y = np.sin(2 * np.pi * (x - 0.01 * i))
  line.set_data(x, y)
  return line,


# anim = FuncAnimation(fig, animate, frames=200, interval=50)
anim = FuncAnimation(fig, animate, frames=200, interval=100)

plt.show()
```

**FuncAnimation** 클래스의 **interval**을 사용해서 프레임 사이의 간격을 밀리초 (milliseconds) 단위로 지정할 수 있습니다.

디폴트 값은 200이며, 예제에서는 interval 값을 각각 50, 100으로 지정했습니다.

아래와 같은 애니메이션 그래프가 나타납니다.

[![Matplotlib 애니메이션 사용하기 - Interval 설정하기 (interval=50ms)](https://codetorial.net/matplotlib/_images/animation_funcanimation_02_interval_50ms.gif)](https://codetorial.net/matplotlib/_images/animation_funcanimation_02_interval_50ms.gif)

Matplotlib 애니메이션 사용하기 - Interval 설정하기 (interval=50ms)

[![Matplotlib 애니메이션 사용하기 - Interval 설정하기 (interval=100ms)](https://codetorial.net/matplotlib/_images/animation_funcanimation_02_interval_100ms.gif)](https://codetorial.net/matplotlib/_images/animation_funcanimation_02_interval_100ms.gif)

Matplotlib 애니메이션 사용하기 - Interval 설정하기 (interval=100ms)

## 애니메이션 저장하기

```
import numpy as np
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation

fig = plt.figure()
ax = plt.axes(xlim=(0, 4), ylim=(-2, 2))
line, = ax.plot([], [], lw=3)


def animate(i):
    x = np.linspace(0, 4, 1000)
    y = np.sin(2 * np.pi * (x - 0.01 * i))
    line.set_data(x, y)
    return line,


# anim = FuncAnimation(fig, animate, frames=200, interval=50)
anim = FuncAnimation(fig, animate, frames=200, interval=100)

# plt.show()
# anim.save('sine_wave_interval_50ms.gif', writer='imagemagick')
anim.save('sine_wave_interval_100ms.gif', writer='imagemagick')
```



**matplotlib.animation** 모듈의 FuncAnimation 클래스의 **save()** 메서드는 모든 프레임을 애니메이션으로 저장합니다.

Matplotlib 애니메이션을 저장하기 위해서 [ImageMagick](https://imagemagick.org/script/download.php)을 사용합니다.

**Windows** 환경에서는 아래 그림의 파일을 다운받아서 실행하면 설치가 진행됩니다.

[![Matplotlib 애니메이션 사용하기 - ImageMagick 설치하기](https://codetorial.net/matplotlib/_images/animation_funcanimation_03.png)](https://codetorial.net/matplotlib/_images/animation_funcanimation_03.png)

Matplotlib 애니메이션 사용하기 - ImageMagick 설치하기

**Ubuntu** 환경 (Google Colaboratory)에서는 아래의 명령어로 ImageMagick을 설치할 수 있습니다.

```
!apt install imagemagick
```



**save()** 메서드에 **writer=’imagemagick’**과 같이 지정해주고, save() 메서드를 호출하면 지정한 파일명의 **.gif** 파일이 지정한 경로에 저장됩니다.

[![Matplotlib 애니메이션 사용하기 - 애니메이션 저장하기](https://codetorial.net/matplotlib/_images/animation_funcanimation_04.png)](https://codetorial.net/matplotlib/_images/animation_funcanimation_04.png)





## **ArtistAnimation** 

이번에는 **matplotlib.animation** 모듈의 **ArtistAnimation** 클래스를 사용해서 그래프를 애니메이션으로 표현하는 방법에 대해 소개합니다.

```
import numpy as np
import matplotlib.pyplot as plt
import matplotlib.animation as animation

fig, ax = plt.subplots()

x = np.linspace(0, 2 * np.pi, 100)
y = np.linspace(0, 2 * np.pi, 100).reshape(-1, 1)

ims = []
for i in range(100):
    x += np.pi / 20
    y += np.pi / 20
    im = ax.imshow(np.sin(x) + np.cos(y), animated=True)
    if i == 0:
        ax.imshow(np.sin(x) + np.cos(y))
    ims.append([im])

ani = animation.ArtistAnimation(fig, ims, interval=100)

plt.show()
```

[np.linspace(a, b, n)](https://codetorial.net/numpy/functions/numpy_linspace.html)는 a부터 b 사이를 균일한 간격으로 나누는 숫자 n개를 반환합니다.

**np.pi**는 ππ를 나타내는 [NumPy 상수](https://codetorial.net/numpy/numpy_constants.html)입니다.

**imshow()**는 숫자 데이터 어레이를 이미지로 표현하는 함수입니다.

각기 다른 데이터를 **imshow()** 함수를 사용해서 이미지로 나타내고, **ims** 리스트에 추가했습니다.

**ArtistAnimation** 클래스는 이미지의 리스트를 각각의 프레임을 갖는 애니메이션으로 변환합니다.

아래와 같은 애니메이션이 나타납니다.

[![Matplotlib 애니메이션 사용하기 - 기본 사용](https://codetorial.net/matplotlib/_images/animation_artistanimation_01.gif)](https://codetorial.net/matplotlib/_images/animation_artistanimation_01.gif)

Matplotlib 애니메이션 사용하기 - 기본 사용

## 애니메이션 저장하기



```
import numpy as np
import matplotlib.pyplot as plt
import matplotlib.animation as animation

fig, ax = plt.subplots()

x = np.linspace(0, 2 * np.pi, 100)
y = np.linspace(0, 2 * np.pi, 100).reshape(-1, 1)

ims = []
for i in range(100):
    x += np.pi / 20
    y += np.pi / 20
    im = ax.imshow(np.sin(x) + np.cos(y), animated=True)
    if i == 0:
        ax.imshow(np.sin(x) + np.cos(y))
    ims.append([im])

ani = animation.ArtistAnimation(fig, ims, interval=100)

ani.save('sin_plus_cos.gif', writer='imagemagick')
# plt.show()
```



**matplotlib.animation** 모듈의 ArtistAnimation 클래스의 **save()** 메서드는 모든 프레임을 애니메이션으로 저장합니다.

Matplotlib 애니메이션을 저장하기 위해서 [ImageMagick](https://imagemagick.org/script/download.php)을 사용합니다.

이전 페이지와 마찬가지로 **writer=’imagemagick’**과 같이 지정해주고, **save()** 메서드를 호출하면 지정한 파일명의 **.gif** 파일이 지정한 경로에 저장됩니다.

[![Matplotlib 애니메이션 사용하기 - 애니메이션 저장하기](https://codetorial.net/matplotlib/_images/animation_artistanimation_02.png)](https://codetorial.net/matplotlib/_images/animation_artistanimation_02.png)







# Matplotlib 3차원 Surface 표현하기

[![Matplotlib 3차원 Surface 표현하기](https://codetorial.net/matplotlib/_images/3d_plot_surface_00.png)](https://codetorial.net/matplotlib/_images/3d_plot_surface_00.png)



이 페이지에서는 **plot_surface()** 함수의 사용법을 소개합니다.

**plot_surface()** 함수를 사용해서 2차원 어레이를 3차원 Surface로 표현할 수 있습니다.

```
from mpl_toolkits.mplot3d import axes3d
import matplotlib.pyplot as plt
import numpy as np


fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

x = np.linspace(-10, 10, 11)
X = np.tile(x, (11, 1))
Y = np.transpose(X)
Z = np.random.rand(11, 11)

ax.plot_surface(X, Y, Z)
ax.set_zlim(-10, 10)

plt.tight_layout()
plt.show()
```

3차원 Axes 객체 (Axes3D)를 사용하기 위해 우선 **from mpl_toolkits.mplot3d.axes3d** 모듈을 Import 합니다.

**add_subplot()**의 **projection=’3d’** 키워드를 사용해서 Axes3D 객체를 생성합니다.

Axes3D 객체의 **plot_surface()** 함수는 2차원 어레이 형태 X, Y, Z를 3차원 Surface로 표현합니다.

X, Y는 -10에서 10 범위에서 11개의 값을 갖도록 만들어진 2차원 어레이입니다.

[np.linspace](https://codetorial.net/numpy/functions/numpy_linspace.html), [np.tile](https://codetorial.net/numpy/functions/numpy_tile.html), [np.transpose](https://codetorial.net/numpy/functions/numpy_transpose.html) 함수의 사용에 대해서는 링크를 참고하세요.

Z는 0에서 1사이의 값을 갖는 2차원 난수 어레이입니다.

[np.random.rand](https://codetorial.net/numpy/random.html#random-rand) 함수의 사용에 대해서는 링크를 참고하세요.

**set_zlim()**을 사용해서 Z축의 범위를 -10에서 10으로 지정했습니다.

[![Matplotlib 3차원 Surface 표현하기 - 기본 사용](https://codetorial.net/matplotlib/_images/3d_plot_surface_01.png)](https://codetorial.net/matplotlib/_images/3d_plot_surface_01.png)



```
# from mpl_toolkits.mplot3d import axes3d
import matplotlib.pyplot as plt
import numpy as np


fig, ax = plt.subplots(subplot_kw={"projection": "3d"})
#fig = plt.figure()
#ax = fig.add_subplot(111, projection='3d')

x = np.linspace(-10, 10, 11)
X = np.tile(x, (11, 1))
Y = np.transpose(X)
Z = np.random.rand(11, 11)

ax.plot_surface(X, Y, Z)
ax.set_zlim(-10, 10)

plt.tight_layout()
plt.show()
```

Matplotlib 3.2.0 버전부터 **from mpl_toolkits.mplot3d import axes3d**를 명시적으로 Import하지 않아도 됩니다. ([참고](https://matplotlib.org/3.3.1/tutorials/toolkits/mplot3d.html))

예제2와 예제1은 같은 결과를 보여줍니다.

## 축 눈금 지정하기

```
from mpl_toolkits.mplot3d import axes3d
import matplotlib.pyplot as plt
import numpy as np


fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

x = np.linspace(-10, 10, 11)
X = np.tile(x, (11, 1))
Y = np.transpose(X)
Z = np.random.rand(11, 11)
Z2 = 1.5 * np.random.rand(11, 11) + 2
Z3 = np.random.rand(11, 11) - 2

ax.plot_surface(X, Y, Z)
ax.plot_surface(X, Y, Z2)
ax.plot_surface(X, Y, Z3)
ax.set_zlim(-10, 10)
ax.set_xticks([-10, -5, 0, 5, 10])
ax.set_yticks([-10, -5, 0, 5, 10])
ax.set_zticks([-10, -5, 0, 5, 10])

plt.tight_layout()
plt.show()
```

이번에는 세 개의 2차원 어레이를 3차원 Surface로 표현했습니다.

**set_xticks()**, **set_yticks()**, **set_zticks()**는 X, Y, Z축의 눈금의 위치를 지정합니다.

결과는 아래와 같습니다.

[![Matplotlib 3차원 Surface 표현하기 - 축 눈금 지정하기](https://codetorial.net/matplotlib/_images/3d_plot_surface_02.png)](https://codetorial.net/matplotlib/_images/3d_plot_surface_02.png)



## 컬러맵, 컬러바 사용하기

```
from mpl_toolkits.mplot3d import axes3d
import matplotlib.pyplot as plt
import numpy as np


fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

x = np.linspace(-10, 10, 11)
X = np.tile(x, (11, 1))
Y = np.transpose(X)
Z = 2 * np.random.rand(11, 11) - 1

surf = ax.plot_surface(X, Y, Z, cmap='viridis')
ax.set_zlim(-5, 5)
ax.set_xticks([-10, -5, 0, 5, 10])
ax.set_yticks([-10, -5, 0, 5, 10])
ax.set_zticks([-5, 0, 5])

fig.colorbar(surf, shrink=0.6, aspect=8)
surf.set_clim(-1.0, 1.0)
plt.tight_layout()
plt.show()
```



**plot_surface()** 함수의 **cmap**은 3차원 Surface의 컬러맵을 지정합니다.

**colorbar()**를 호출하면 그래프에 컬러바를 표시합니다.

**shrink**는 컬러바의 크기, **aspect**는 컬러바의 종횡비를 지정합니다.

아래와 같은 그래프가 만들어집니다.

[![Matplotlib 3차원 Surface 표현하기 - 컬러바 표시하기](https://codetorial.net/matplotlib/_images/3d_plot_surface_03.png)](https://codetorial.net/matplotlib/_images/3d_plot_surface_03.png)

