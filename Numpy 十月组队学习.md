# Numpy 十月组队学习

## 常量

numpy.nan == numpy.nan -> False

![image-20201020214108749](upload\image-20201020214108749.png)

import numpy as np

print(np.nan == np.nan) # False
print(np.nan != np.nan) # True  



## 创建数据类型

numpy 的数值类型实际上是 dtype 对象的实例。

![image-20201020214245884](upload\image-20201020214245884.png)

class dtype(object):
	def __init__(self, obj, align=False, copy=False):
		pass  

