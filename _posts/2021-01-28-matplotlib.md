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







# Matplotlib x, y 값 입력하기



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













# Matplotlib 마커 지정하기

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