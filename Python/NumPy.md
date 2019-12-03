# NumPy
## 安装
```bash
# Mac
brew install numpy

# Linux
pip install numpy
```
## 创建NumPy数组
```python
import numpy as np

# 创建已知元素的数组
a = np.array([1, 2, 3, 4])

# 创建线性增加的数组
b = np.arange(5)  # b = [0, 1, 2, 3, 4]
c = np.arange(10, 35, 3)  # c = [10, 13, 16, 19, 22, 25, 28, 31, 34]

# 创建全0或全1数组
d = np.zeros((2, 4))
e = np.zeros((2, 4))

# 创建均匀间隔的数组
f = np.linspace(0, 10, 5)  # f = [0, 2, 4, 6, 8, 10]
f = np.linspace(0, 10, num=5)

# 创建全是定值的数组
g = np.full((2, 2), 3)  # g = [[3, 3], [3, 3]]

# 创建对角线为1其余为0的数组
h = np.eye(3,3)

# 创建随机数组
import random
i = np.random.random((2, 3))
```
> `numpy`数组中一维数组不像`Matlab`中`shape`为`(n, 1)`  
> 若要产生列向量或者行向量，需要用二维数组  
> ```py
a = np.array([[1,2,3]]) # shape = (1,3)
b = np.array([1,2,3])   # shape = (3, )
```

## 数组操作
```py
# reshape
arr = np.arange(10)
arr.reshape(2, -1) # -1表示程序自动计算

# 
```
