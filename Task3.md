# 1 dict字典
## 1.1 定义
字典dict，是Python唯一的标准mapping类型，也是内置在Python解释器中的。
## 1.2 创建
字典的每个值都具备自己独有的名称即键(key), 每个 key 都有对应的值(value)<br>
字典中的key和value必须成对出现。整个字典包括在花括号‘{ }’中，它的每个键值(key=>value)对使用冒号(:)分割，每对值之间用逗号(,)分割。
    
    d = {key1 : value1, key2 : value2 }
    
定义如记录人员成绩的字典，如下：
    
    d = {'Woodman': 95, 'Alan': 85, 'Bobo': 59}

## 1.3 方法
| 序号 | 函数及描述 |
| -- | ----- |
| 1  | dict.clear() |  删除字典内所有元素 |
| 2  | dict.copy() | 返回一个字典的浅复制 |
| 3  | dict.fromkeys() | 创建一个新字典，以序列seq中元素做字典的键，val为字典所有键对应的初始值 |
| 4  | dict.get(key, default=None) | 返回指定键的值，如果值不在字典中返回default值 |
| 5  | key in dict | 如果键在字典dict里返回true，否则返回false |
| 6  | dict.items() | 以列表返回可遍历的(键, 值) 元组数组 |
| 7  | dict.keys() | 返回一个迭代器，可以使用 list() 来转换为列表 |
| 8  | dict.setdefault(key, default=None) | 和get()类似, 但如果键不存在于字典中，将会添加键并将值设为default |
| 9  | dict.update(dict2) | 把字典dict2的键/值对更新到dict里 |
| 10 | dict.values() | 返回一个迭代器，可以使用 list() 来转换为列表 |
| 11 | pop(key[,default]) | 删除字典给定键 key 所对应的值，返回值为被删除的值。key值必须给出。 否则，返回default值。 |
| 12 | popitem() | 随机返回并删除字典中的一对键和值(一般删除末尾对 |)。

# 2 集合
## 2.1 定义
集合（set）是一个**无序的不重复**元素序列。
## 2.2 创建
可以使用大括号 { } 或者 set() 函数创建集合。<br>
注意：创建一个空集合必须用 set() 而不是 { }，因为 { } 是用来创建一个空字典。
    
    parame = {value01,value02,...}
或者

    set(value)

## 2.3 方法
| 方法 | 描述 |
| -- | -- |
| add() | 为集合添加元素 |
| clear() | 移除集合中的所有元素 |
| copy() | 拷贝一个集合 |
| difference() | 返回多个集合的差集 |
| difference_update() | 移除集合中的元素，该元素在指定的集合也存在。 |
| discard() | 删除集合中指定的元素 |
| intersection() | 返回集合的交集 |
| intersection_update() | 删除集合中的元素，该元素在指定的集合中不存在。 |
| isdisjoint() | 判断两个集合是否包含相同的元素，如果没有返回 True，否则返回 False。 |
| issubset() | 判断指定集合是否为该方法参数集合的子集。 |
| issuperset() | 判断该方法的参数集合是否为指定集合的子集 |
| pop() | 随机移除元素 |
| remove() | 移除指定元素 |
| symmetric_difference() | 返回两个集合中不重复的元素集合。 |
| symmetric_difference_update() | 移除当前集合中在另外一个指定集合相同的元素，并将另外一个指定集合中不同的元素插入到当前集合中。 |
| union() | 返回两个集合的并集 |
| update() | 给集合添加元素 |

# 3 判断语句
    if condition_1:
        statement_block_1
    elif condition_2:
        statement_block_2
    else:
        statement_block_3
如果 "condition_1" 为 True 将执行 "statement_block_1" 块语句<br>
如果 "condition_1" 为False，将判断 "condition_2"<br>
如果 "condition_2" 为 True 将执行 "statement_block_2" 块语句<br>
如果 "condition_2" 为False，将执行"statement_block_3"块语句<br>
也可以嵌套使用

    if 表达式1:
        语句
        if 表达式2:
            语句
        elif 表达式3:
            语句
        else:
            语句
    elif 表达式4:
        语句
    else:
        语句
    
## 4 三目表达式


    #如果条件为真，返回真 否则返回假
    condition_is_true if condition else condition_is_false

举例
 
    a = 1
    b = 2
    h = ""
    
    h = a-b if a>b else a+b
    
    print(h)

# 5 循环语句
## 5.1 while循环

    while 判断条件：
        语句
可使用else

    while 判断条件：
        语句
    else
        语句
          
## 5.2 for循环
for循环可以遍历任何序列的项目，如一个列表或者一个字符串。

for循环的一般格式如下：

    for <variable> in <sequence>:
        <statements>
    else:
        <statements>
        
for循环中可以用range()提取不同步长或者指定区间的值

## 5.3 循环中的跳出和继续下一个循环
break 语句可以跳出 for 和 while 的循环体。如果你从 for 或 while 循环中终止，任何对应的循环 else 块将不执行。
continue语句被用来告诉Python跳过当前循环块中的剩余语句，然后继续进行下一轮循环。

