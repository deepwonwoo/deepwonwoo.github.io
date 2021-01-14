---
layout: post
title: "Binary Search Tree"
date: 2021-01-08
categories: Python
tags: [Python, Algorithm, Tree]
---



# Tree란❓

: Node와 Branch를 이용해서 사이클을 이루지 않도록 구성한 데이터 구조.

- 최대 두개의 자식 노드를 가진 트리 형태의 자료 구조로 단순히 값을 저장하는 용도보다는 효율적인 탐색이나 정렬을 위해 사용한다.
- 주어진 값이나 이보다 작거나 큰 값들을 평균 O(log n)의 시간 복잡도로 탐색 가능하다.

> ✔️ 기본 용어
> Node: 트리에서 데이터를 저장하는 기본 요소
> Root Node : 트리 맨 위에 있는 노드
> Level : 최상위 노드를 level 0 으로 하였을 때, 하위 branch로 연결된 노드의 깊이
> Parent Node : 어떤 노드의 다음 레벨에 연결된 노드
> Child Node : 어떤 노드의 상위 레벨에 연결되 노드
> Leaf Node : Child Node 가 하나도 없는 노드
> Sibling : 동일한 Parent Node를 가진 노드
> Depth : 트리에서 Node가 가질 수 있는 최대 level



# 이진탐색Tree

: 모든 노드에 대하여 왼쪽 자식 노드들의 값이 현재 노드보다 값이 작거나 같으며, 오른쪽 자식 노느들의 값이 현재 노드의 값보다 크다는 조건을 만족하여야 한다.

* 이진탐색의 효율적인 탐색 능력을 유지하면서도, 빈번한 자료 입력과 삭제를 가능하다.
* 맨 먼저 입력된 값이 root 노드가 되며 그 다음부터는 입력값과 노드 간 대소관계에 따라 입력값의 노드 위치가 달라진다.
* 이진 탐색 트리는 트리의 좌우 균형이 맞는다면 정렬된 배열보다 효과적으로 원하는 값을 탐색할 수 있다.
* 그 중 예외인 경우는 이진트리에 오름차순이던, 내림차순이던 정렬된 데이터가 입력되면 한쪽으로 치우친 (skewed) 트리가 만들어지기 때문에 최악의 경우 모든 데이터를 살펴야 할수도 있어 시간복잡도가 O(n)이 된다.



## 클래스 정의

- 이진 탐색 트리 구현시에는 먼저 Node 클래스를 정의해야 하는데, 노드 값인 self.data와 왼쪽 / 오른쪽 노드인 self.left, self.right의 속성을 가진다.
- 초기화시에는 데이터의 값만 주어지고 좌우 노드는 비어있게된다

```python
class Node:
	def __init__(self, data):
		self.data = data
		self.left = self.right = None
```

- Node 클래스를 사용해 이진 탐색 트리 클래스를 구현하고 여기에 원소를 추가, 삭제, 탐색할 수 있도록 insert(), delete(), find() 메서드를 추가한다.

```python
class BinaryTree:
    def __init__(self):
        self.root = None
```

### insert()

```python
class BinaryTree:
    ...
    def insert(self, data):
        self.root = self._insert_value(self.root, data)
        return self.root is not None

    def _insert_value(self, node, data):
        if node is None:
            node = Node(data)
        else:
            if data <= node.data:
                node.left = self._insert_value(node.left, data)
            else:
                node.right = self._insert_value(node.right, data)
        return node
```

#### find()

- 원하는 값의 존재 유무를 확인할 수 있도록 재귀와 값의 대소 관계를 비교하여 구현한다.

```python
class BinarySearchTree():
    ...
    def find(self, key):
        return self._find_value(self.root, key)

    def _find_value(self, root, key):
        if root is None or root.data == key:
            return root is not None
        elif key < root.data:
            return self._find_value(root.left, key)
        else:
            return self._find_value(root.right, key)
```





## 순회

### **전위순회**

: 전위순회 순서는 NLR이다 (N은 현재노드, L은 왼쪽 서브트리, R은 오른쪽 서브트리)



```python
def preorder(self, n):
    if n != None:
        print(n.data)  # node 방문
        if n.left:
            self.preorder(n.left)  # 왼쪽 서브트리 순회
        if n.right:
            self.preorder(n.right)  # 오른쪽 서브트리 순회
```



### **레벨 순회**

: 레벨순회의 순회방법

```
def levelorder(self, root):
	q=[]
	q.append(root)
	while q:
		t=q.pop(0)
        print(n.data)  # node 방문
        if t.left != None:
            q.append(t.left)  # 왼쪽 자식 큐에 삽입
        if t.right != None:
        	q.append(q.right)  # 오른쪽 자식 큐에 삽입
```

