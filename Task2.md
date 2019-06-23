# 1. 列表
## 1.1 标志
列表可以作为一个方括号内的逗号分隔值出现。
## 1.2 基本操作
### 1.2.1 创建
    list = ['datawhale','python','analysis'];
### 1.2.2 append 在列表末尾添加新的对象
    list.append('nlp')
### 1.2.3 append 移除列表中的一个元素（默认最后一个元素），并且返回该元素的值
    list.pop(2);
### 1.2.4 del 删除列表元素
    del list[2];
### 1.2.5 copy 
    list2 = list.copy();
### 1.3 列表相关方法
| 序号	| 方法 |
| -- | -- |
| 1	| list.append(obj)<br>在列表末尾添加新的对象 | 
| 2	| list.count(obj)<br>统计某个元素在列表中出现的次数| 
| 3	| list.extend(seq)<br>在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表）| 
| 4	| list.index(obj)<br>从列表中找出某个值第一个匹配项的索引位置| 
| 5	| list.insert(index, obj)<br>将对象插入列表| 
| 6	| list.pop([index=-1])<br>移除列表中的一个元素（默认最后一个元素），并且返回该元素的值| 
| 7	| list.remove(obj)<br>移除列表中某个值的第一个匹配项| 
| 8	| list.reverse()<br>反向列表中元素| 
| 9	| list.sort( key=None, reverse=False)<br>对原列表进行排序| 
| 10	| list.clear()<br>清空列表| 
| 11	| list.copy()<br>复制列表| 

# 2. 元组
## 2.1 标志
Python 的元组与列表类似，*不同之处在于元组的元素不能修改*。
## 2.2 基本操作
### 2.2.1 创建
元组使用小括号，列表使用方括号。
    cellArray = ('datawhale','python','analysis');
### 2.2.2 不可变性
元组中的元素值是不允许修改的，但我们可以对元组进行连接组合

# 3.string字符串
## 3.1 定义
字符串是 Python 中最常用的数据类型。我们可以使用引号( ' 或 " )来创建字符串。
    
    string1 = 'Datawhale Course';
## 3.2 +
字符串可以截取一部分并与其他字段拼接
    
    string2 = string1[:10]+'Crew';
## 3.3 *
重复输出字符串
    
    string3 = string1*2

## 3.3 读取方式
使用[]读取特定位置的字符
    
    string4 = string1[:10];

## 3.4 字符串相关方法
| 序号	| 方法及描述 | 
| -- | ----- |
| 1 | capitalize()<br>将字符串的第一个字符转换为大写| 
| 2	| center(width, fillchar)<br>返回一个指定的宽度 width 居中的字符串，fillchar 为填充的字符，默认为空格。| 
| 3	| count(str, beg= 0,end=len(string))<br>返回 str 在 string 里面出现的次数，如果 beg 或者 end 指定则返回指定范围内 str 出现的次数| 
| 4	| bytes.decode(encoding="utf-8", errors="strict")<br>Python3 中没有 decode 方法，但我们可以使用 bytes 对象的 decode() 方法来解码给定的 bytes 对象，这个 bytes 对象可以由 str.encode() 来编码返回。| 
| 5	| encode(encoding='UTF-8',errors='strict')<br>以 encoding 指定的编码格式编码字符串，如果出错默认报一个ValueError 的异常，除非 errors 指定的是'ignore'或者'replace'| 
| 6	| endswith(suffix, beg=0, end=len(string))<br>检查字符串是否以 obj 结束，如果beg 或者 end 指定则检查指定的范围内是否以 obj 结束，如果是，返回 True,否则返回 False.| 
| 7	| expandtabs(tabsize=8)<br>把字符串 string 中的 tab 符号转为空格，tab 符号默认的空格数是 8 。| 
| 8	| find(str, beg=0, end=len(string))<br>检测 str 是否包含在字符串中，如果指定范围 beg 和 end ，则检查是否包含在指定范围内，如果包含返回开始的索引值，否则返回-1| 
| 9	| index(str, beg=0, end=len(string))<br>跟find()方法一样，只不过如果str不在字符串中会报一个异常.| 
| 10	| isalnum()<br>如果字符串至少有一个字符并且所有字符都是字母或数字则返 回 True,否则返回 False| 
| 11	| isalpha()<br>如果字符串至少有一个字符并且所有字符都是字母则返回 True, 否则返回 False| 
| 12	| isdigit()<br>如果字符串只包含数字则返回 True 否则返回 False..| 
| 13	| islower()<br>如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是小写，则返回 True，否则返回 False| 
| 14	| isnumeric()<br>如果字符串中只包含数字字符，则返回 True，否则返回 False| 
| 15	| isspace()<br>如果字符串中只包含空白，则返回 True，否则返回 False.| 
| 16	| istitle()<br>如果字符串是标题化的(见 title())则返回 True，否则返回 False| 
| 17	| isupper()<br>如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是大写，则返回 True，否则返回 False| 
| 18	| join(seq)<br>以指定字符串作为分隔符，将 seq 中所有的元素(的字符串表示)合并为一个新的字符串| 
| 19	| len(string)<br>返回字符串长度|  
| 20	| ljust(width[, fillchar])<br>返回一个原字符串左对齐,并使用 fillchar 填充至长度 width 的新字符串，fillchar 默认为空格。| 
| 21	| lower()<br>转换字符串中所有大写字符为小写.| 
| 22	| lstrip()<br>截掉字符串左边的空格或指定字符。| 
| 23	| maketrans()<br>创建字符映射的转换表，对于接受两个参数的最简单的调用方式，第一个参数是字符串，表示需要转换的字符，第二个参数也是字符串表示转换的目标。| 
| 24	| max(str)<br>返回字符串 str 中最大的字母。| 
| 25	| min(str)<br>返回字符串 str 中最小的字母。| 
| 26	| replace(old, new [, max])<br>把 将字符串中的 str1 替换成 str2,如果 max 指定，则替换不超过 max 次。| 
| 27	| rfind(str, beg=0,end=len(string))<br>类似于 find()函数，不过是从右边开始查找.| 
| 28	| rindex( str, beg=0, end=len(string))<br>类似于 index()，不过是从右边开始.| 
| 29	| rjust(width,[, fillchar])<br>返回一个原字符串右对齐,并使用fillchar(默认空格）填充至长度 width 的新字符串| 
| 30	| rstrip()<br>删除字符串字符串末尾的空格.| 
| 31	| split(str="", num=string.count(str))<br>num=string.count(str)) 以 str 为分隔符截取字符串，如果 num 有指定值，则仅截取 num+1 个子字符串| 
| 32	| splitlines([keepends])<br>按照行('\r', '\r\n', \n')分隔，返回一个包含各行作为元素的列表，如果参数 keepends 为 False，不包含换行符，如果为 True，则保留换行符。| 
| 33	| startswith(substr, beg=0,end=len(string))<br>检查字符串是否是以指定子字符串 substr 开头，是则返回 True，否则返回 False。如果beg 和 end 指定值，则在指定范围内检查。| 
| 34	| strip([chars])<br>在字符串上执行 lstrip()和 rstrip()| 
| 35	| swapcase()<br>将字符串中大写转换为小写，小写转换为大写| 
| 36	| title()<br>返回"标题化"的字符串,就是说所有单词都是以大写开始，其余字母均为小写(见 istitle())| 
| 37	| translate(table, deletechars="")<br>根据 str 给出的表(包含 256 个字符)转换 string 的字符, 要过滤掉的字符放到 deletechars 参数中| 
| 38	| upper()<br>转换字符串中的小写字母为大写| 
| 39	| zfill (width)<br>返回长度为 width 的字符串，原字符串右对齐，前面填充0| 
| 40	| isdecimal()<br>检查字符串是否只包含十进制字符，如果是返回 true，否则返回 false。| 

## 3.5字符串格式化
| 符号	| 描述| 
| -- | -- |
|       %c	|  格式化字符及其ASCII码| 
|      %s	|  格式化字符串| 
|     %d	|  格式化整数| 
|    %u	|  格式化无符号整型| 
|   %o	|  格式化无符号八进制数| 
|  %x	|  格式化无符号十六进制数| 
|       %X	 | 格式化无符号十六进制数（大写）| 
|      %f	|  格式化浮点数字，可指定小数点后的精度| 
|     %e	|  用科学计数法格式化浮点数| 
|    %E	|  作用同%e，用科学计数法格式化浮点数| 
|   %g	|  %f和%e的简写| 
|   %G	|  %f 和 %E 的简写| 
| %p	|  用十六进制数格式化变量的地址| 



