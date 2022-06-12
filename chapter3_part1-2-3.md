```python
# 元组的另一种表示方法
tup = 4,5,6
tup
```




    (4, 5, 6)




```python
nested_up = (4,5,6),(7,8,9)
nested_up
```




    ((4, 5, 6), (7, 8, 9))




```python
# tuple函数 将任意序列转化为元组
tuple([4,5,6,7,8])
```




    (4, 5, 6, 7, 8)




```python
tuple('string')
```




    ('s', 't', 'r', 'i', 'n', 'g')




```python
"""
元组创建，无法改变其中的元素
"""
tup = tuple(['foo', [1,2,3,4], True])
tup
tup[-1] = False  # 报错
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp/ipykernel_31064/1230417048.py in <module>
          4 tup = tuple(['foo', [1,2,3,4], True])
          5 tup
    ----> 6 tup[-1] = False  # 报错
    

    TypeError: 'tuple' object does not support item assignment



```python
# 元组对象中含有可变对象，如列表、字典、字符串，可以在对象内部改变
tup[1].append(3)
tup
```




    ('foo', [1, 2, 3, 4, 3], True)




```python
# 通过+令元组加长
(1,2,3,4,5,6) + (7,8,9) + ('bar',) # 必须加个逗号，不然报错
```




    (1, 2, 3, 4, 5, 6, 7, 8, 9, 'bar')




```python
# 元组x整数，复制多份元组内容，数组同理
(1,2,3,4,5,6)*3
```




    (1, 2, 3, 4, 5, 6, 1, 2, 3, 4, 5, 6, 1, 2, 3, 4, 5, 6)




```python
[1,2,3,4,5,6]*3
```




    [1, 2, 3, 4, 5, 6, 1, 2, 3, 4, 5, 6, 1, 2, 3, 4, 5, 6]




```python
# 元组拆包，提取元素
tup = ('string', [1,2,3,4], 4)
tup
a, b, c = tup
```


```python
a
```




    'string'




```python
b
```




    [1, 2, 3, 4]




```python
c
```




    4




```python
junk = tuple(['foo', [1,2,3,4], True])
junk
d,e,f = junk
d
```




    'foo'




```python
e
```




    [1, 2, 3, 4]




```python
f
```




    True




```python
# 利用元组交换变量名
a, b = 1,2
a
```




    1




```python
b
```




    2




```python
b,a = a,b # 互换元素
a
```




    2




```python
b
```




    1




```python
# 利用拆包遍历元组、列表组成的序列
seq = [(1,2,3), (4,5,6), (7,8,9)]
for a,b,c in seq:
    print(a)
    print(b)
    print(c)
    print('a={0}, b={1}, c={2}'.format(a,b,c))
```

    1
    2
    3
    a=1, b=2, c=3
    4
    5
    6
    a=4, b=5, c=6
    7
    8
    9
    a=7, b=8, c=9
    


```python
# *rest，拆包工具，表示剩下的元素，返回列表
values = 1,2,3,4,5,6
a, b, *rest = values
a, b
```




    (1, 2)




```python
rest
```




    [3, 4, 5, 6]




```python
# *_，不想要后面的数据
a, b, *_ = values
a, b
```




    (1, 2)




```python
# count函数，计算某个元素的出现次数
values.count(3)
```




    1




```python
values.count('7')
```




    0




```python
values = [1,2,3,4,5,6,7,8]
values.count(4)
```




    1




```python
values = 'string'
values.count('b')
```




    0




```python
# list 列表，可变可修改
tup = ('string', [1,2,3,4], 4)
b_list = list(tup)
b_list
```




    ['string', [1, 2, 3, 4], 4]




```python
# extend，列表添加多个元素，扩展原列表
x = [4, None, 'junk']
x.extend([7, 8, (2,3,4), 'string', [0,1,2]])
x
```




    [4, None, 'junk', 7, 8, (2, 3, 4), 'string', [0, 1, 2]]




```python
# sort函数 排序
b = ['saw', 'small', 'he', 'foxes', 'hee']
b.sort() # 按照首字母顺序排序
b
```




    ['foxes', 'he', 'hee', 'saw', 'small']




```python
b.sort(key = len)  # 按照元素长度排列
b
```




    ['he', 'hee', 'saw', 'foxes', 'small']




```python
b[::-1]  # 倒序排列
```




    ['small', 'foxes', 'saw', 'hee', 'he']




```python
# 二分搜索、维护已排序的列表
# 未排序的列表不会报错，有可能结果不对
import bisect
c = [1, 2, 2, 2, 3, 4, 7]

"""
bisect.bisect 按列表从大到小顺序，元素应放到第几位
"""
bisect.bisect(c, 2) # 在列表c中，2应在第几位
```




    4




```python
c # bisect.bisect不改变原来的列表
```




    [1, 2, 2, 2, 3, 4, 7]




```python
bisect.bisect(c, 5)
```




    6




```python
c
```




    [1, 2, 2, 2, 3, 4, 7]




```python
"""
bisect.insort 
把元素插到第几位，返回插入数字后的列表
"""
import bisect
c = [1, 2, 2, 2, 3, 4, 7]
bisect.insort(c, 666)
c
```




    [1, 2, 2, 2, 3, 4, 7, 666]




```python
## 列表切片
seq = [1,2,5,6,3,7,8,9]

# 列表翻转
seq[::-1]
```




    [9, 8, 7, 3, 6, 5, 2, 1]




```python
# enumerate函数，提取列表的元素和索引

# 提取列表的元素和索引，形成字典
array = ['a', 'b', 'c']
mapping = {}
for key, value in enumerate(array):
    mapping[key] = value
mapping
```




    {0: 'a', 1: 'b', 2: 'c'}




```python
# sorted函数，元素排序，返回列表
sorted('I love junk.')
```




    [' ', ' ', '.', 'I', 'e', 'j', 'k', 'l', 'n', 'o', 'u', 'v']




```python
a = (1,2,3)
sorted(a)
```




    [1, 2, 3]




```python
sorted(mapping) #按照字典中的键排序
```




    [0, 1, 2]




```python
# zip函数，元素组合，取短
a = ['a0', 'a1', 'a2']
b = ['b0', 'b1', 'b2', 'b3']
c = ('c0', 'c1', 'c2')
d = '0123456'
e = {'e1': 'v1', 'e2': 'v2', 'e3': 'v3'}
```


```python
del list  #释放list
```


```python
ab = zip(a, b)
list(ab)
```




    [('a0', 'b0'), ('a1', 'b1'), ('a2', 'b2')]




```python
ac = zip(a, c)
list(ac)
```




    [('a0', 'c0'), ('a1', 'c1'), ('a2', 'c2')]




```python
ad = zip(a, d)
list(ad)
```




    [('a0', '0'), ('a1', '1'), ('a2', '2')]




```python
ae = zip(a, e)  #取字典的键
list(ae)
```




    [('a0', 'e1'), ('a1', 'e2'), ('a2', 'e3')]




```python
# 将zip拆包
print(*zip(a, b))
```

    ('a0', 'b0') ('a1', 'b1') ('a2', 'b2')
    


```python
print(*zip(a, c))
```

    ('a0', 'c0') ('a1', 'c1') ('a2', 'c2')
    


```python
print(*zip(a, d))
```

    ('a0', '0') ('a1', '1') ('a2', '2')
    


```python
print(*zip(a, e))
```

    ('a0', 'e1') ('a1', 'e2') ('a2', 'e3')
    


```python
# zip和enumerate共同使用
seq1 = ['a', 'b', 'c']
seq2 = ['e', 'f', 'g']
for i, (a,b) in enumerate(zip(seq1, seq2)):
    print('{0}: {1}, {2}'.format(i, a, b))
```

    0: a, e
    1: b, f
    2: c, g
    


```python
a1 = ('a', 'b', 'c')
b1 = ('d', 'e', 'f')
a1_b1 = list(zip(a1, b1))
a1_b1
dic = {}
for key, (a, b) in enumerate(a1_b1):
    dic[key] = (a, b)
dic
```




    {0: ('a', 'd'), 1: ('b', 'e'), 2: ('c', 'f')}




```python
# reversed函数，元素倒序排列
seq_1 = reversed(range(1, 11))
list(seq_1)
```




    [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]




```python
## 字典

# 删除键值对
a = {0: 'a', 1: 'b', 2: 'c', 3: 'd'}
del a[1]
a

# 弹出某个位置的值
b = a.pop(0)
a
b
```




    'a'




```python
# 分别出现键和值
a
list(a.keys())
list(a.values())
```




    ['a', 'b', 'c']




```python
# update函数，合并两个字典，key相同值会被覆盖
a.update({2: 'd', 3: 'e', 0: 'f'})
a
```




    {2: 'd', 3: 'e', 4: 'f', 0: 'f'}




```python
# 序列合成字典，也可以用dict表示，返回字典
key_list = [1, 2, 3]
values_list = ['a', 'b', 'c']
dic = {}
for key, value in zip(key_list, values_list):
    dic[key] = value
dic
```




    {1: 'a', 2: 'b', 3: 'c'}




```python
dic = dict(zip(key_list, values_list))
dic
```




    {1: 'a', 2: 'b', 3: 'c'}




```python
dic = dict(zip(range(5), reversed(range(5))))
dic
```




    {0: 4, 1: 3, 2: 2, 3: 1, 4: 0}




```python
# 测试一个键是否在字典中,在返回键值对，不在返回‘不在’
a = {0: 'a', 1: 'b', 2: 'c'}
def check_key(key, dic, default_value):
    if key in dic:
        value = dic[key]
    else:
        value = default_value
    print(value)
check_key(3, a, 'No here')
```

    No here
    


```python
# get()函数是Python字典用于返回键值的函数,如果没有对应的键，返回一个空值
def get_check_key(dic, key, default):
    value = dic.get(key, default)
    print(value)
get_check_key(a, 0, 'No here')
```

    a
    
