# python

## 深拷贝浅拷贝

对象引用

```python
alist = []
num= [2]
alist=num
print(id(num),id(alist))
```

![](/Users/qinjing/Library/Application%20Support/marktext/images/2022-11-21-09-37-36-image.png)

copy()    浅拷贝

```python
num2 = [2, [0, 1]]
alist2 = num2.copy()
num2[1][0] = 'qin' #第二层是浅拷贝，修改后alist2同时修改
num2[0] = [33] #第一层是深拷贝，修改后alist2没有修改
print(num2, alist2)
print(id(num2[1][1]), id(alist2[1][1])) # 第二层ID
print(id(num2[1]), id(alist2[1])) #第一层的列表ID
print(id(num2[0]), id(alist2[0])) #第一层的ID
```

![](/Users/qinjing/Library/Application%20Support/marktext/images/2022-11-21-09-34-21-image.png)

深拷贝

```py
import copy
num2 = [2, [0, 1]]
alist2 = copy.deepcopy(num2)
num2[1][0] = 'qin' #第二层是浅拷贝，修改后alist2同时修改
num2[0] = [33] #第一层是深拷贝，修改后alist2没有修改
print(num2, alist2)
print(id(num2[1][1]), id(alist2[1][1])) # 第二层ID
print(id(num2[1]), id(alist2[1])) #第一层的列表ID
print(id(num2[0]), id(alist2[0])) #第一层的ID
```

![](/Users/qinjing/Library/Application%20Support/marktext/images/2022-11-21-09-41-38-image.png)
