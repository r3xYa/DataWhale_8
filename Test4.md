# 1. 函数关键字
在定义 Python 函数时可定义形参（形式参数的意思）， 比如：

    printABC(a,b,c)
    
其中a,b,c就是形式参数<br>
按照形参位置传入的参数被称为**位置参数**， 比如：

    printABC(1,2,3)
此时程序里a=1,b=2,c=3<br>    
如果使用位置参数的方式来传入参数值，则必须严格按照走义函数时指定的顺序来传入参数值；如果根据参数名来传入参数值，则无须遵守定义形参的顺序，这种方式被称为**关键字（keyword）参数**。比如：

    printABC(c=1,a=2,b=3)
此时程序里a=2,b=3,c=1<br>
位置参数与关键字可以混搭,在关键字参数之后的只能是关键字参数。<br>
# 2. 函数的定义
在使用函数之前必须先定义函数，定义函数的语法格式如下：

    def 函数名(形参列表):
        //由零条到多条可执行语句组成的函数
        [return [返回值]]

- **函数名**：从语法角度来看，函数名只要是一个合法的标识符即可；从程序的可读性角度来看，函数名应该由一个或多个有意义的单词连缀而成，每个单词的字母全部小写，单词与单词之间使用下画线分隔。
- **形参列表**：用于定义该函数可以接收的参数。形参列表由多个形参名组成，多个形参名之间以英文逗号（,）隔开。一旦在定义函数时指定了形参列表，调用该函数时就必须传入到应的参数值，也就是说，谁调用函数谁负责为形参赋值。
# 3. 函数参数与作用域
## 3.1 参数默认值
在某些情况下，程序需要在定义函数时为一个或多个形参指定默认值，这样在调用函数时就可以省略为该形参传入参数值，而是直接使用该形参的默认值。<br>
为形参指定默认值的语法格式如下：<br>
形参名 = 默认值, 比如:

    def printABC(c=1,a=2,b=3)
        ......

从上面的语法格式可以看出，形参的默认值紧跟在形参之后，中间以英文“=”隔开。
## 3.2 可变参数
Python 允许在形参前面添加一个星号（*），这样就意味着该参数可接收多个参数值，多个参数值被当成元组传入。比如:

    def printABC(a,*b,**c)
        ......
其中b是带一个支持**普通**参数收集的形参，Python 会将传给 b 参数的多个值收集成一个元组<br>
c是一个支持关键字参数收集的参数, Python 会将这种关键字参数收集成字典
## 3.3 逆向参数收集
所谓逆向参数收集，指的是在程序己有列表、元组、字典等对象的前提下，把它们的元素“拆开”后传给函数的参数。<br>
逆向参数收集需要在传入的列表、**元组参数**之前添加**一个星号**，在**字典参数**之前添加**两个星号**。

    def printABC(a,b,c)
            ......
    myVar = (1,2,3)
    printABC(*myVar)
        
## 3.4 在程序中定义一个变量时，这个变量是有作用范围的，变量的作用范围被称为它的作用域。
根据定义变量的位置，变量分为两种：
- **局部变量**：在函数中定义的变量，包括参数，都被称为局部变量。
-** 全局变量**：在函数外面、全局范围内定义的变量，被称为全局变量。

每个函数在执行时，系统都会为该函数分配一块“临时内存空间”，所有的局部变量都被保存在这块临时内存空间内。当函数执行完成后，这块内存空间就被释放了，这些局部变量也就失效了，因此离开函数之后就不能再访问局部变量了。<br>
全局变量意味着它们可以在所有函数内被访问。
不管是在函数的局部范围内还是在全局范围内，都可能存在多个变量，每个变量“持有”该变量的值。从这个角度来看，不管是局部范围还是全局范围，这些变量和它们的值就像一个“看不见”的字典，其中变量名就是字典的 key，变量值就是字典的 value。

实际上，Python 提供了如下三个工具函数来获取指定范围内的“变量字典”：
- **globals()**：该函数返回全局范围内所有变量组成的“变量字典”。
- **locals()**：该函数返回当前局部范围内所有变量组成的“变量字典”。
- **vars(object)**：获取在指定对象范围内所有变量组成的“变量字典”。如果不传入object 参数，vars() 和 locals() 的作用完全相同。

globals() 和 locals() 看似完全不同，但它们实际上也是有联系的，关于这两个函数的区别和联系大致有以下两点：<br>
locals() 总是获取当前局部范围内所有变量组成的“变量字典”，因此，如果在全局范围内（在函数之外）调用 locals() 函数，同样会获取全局范围内所有变量组成的“变量字典”；而 globals() 无论在哪里执行，总是获取全局范围内所有变量组成的“变量字典”。<br>
一般来说，使用 locals() 和 globals() 获取的“变量字典”只应该被访问，不应该被修改。但实际上，不管是使用 globals() 还是使用 locals() 获取的全局范围内的“变量字典”，都可以被修改，而这种修改会真正改变全局变量本身：但通过 locals() 获取的局部范围内的“变量字典”，即使对它修改也不会影响局部变量。
 
# 4 函数返回值
函数使用return定义返回值
如果程序需要有多个返回值，则既可将多个值包装成列表之后返回，也可直接返回多个值。如果 Python 函数直接返回多个值，Python 会自动将多个返回值封装成元组。

# 5 file
## 5.1 文件打开
Python 提供了一个内置的 open() 函数，该函数用于打开指定文件。
open() 函数的语法格式如下：

    open(file_name [, access_mode] [, buffering])
access_mode有以下这几种模式：

| 模式 | 意义 |
| -- | -- |
| r	| 只读模式 |
| w	| 写模式 |
| a	| 追加模式 |
| +	| 读写模式，可与其他模式结合使用。比如 r+ 代表读写模式，w+ 也代表读写模式 |
| b	| 二进制模式，可与其他模式结合使用。比如 rb 代表二进制只读模式，rb+ 代表二进制读写模式，ab 代表二进制追加模式 |

## 5.2 文件读取
文件对象提供了 read() 方法来按字节或字符读取文件内容，到底是读取宇节还是字符，则取决于是否使用了 b 模式，如果使用了 b 模式，则每次读取一个字节；如果没有使用 b 模式，则每次读取一个字符。在调用该方法时可传入一个整数作为参数，用于指定最多读取多少个字节或宇符。<br>
如果在调用 read() 方法时不传入参数，该方法默认会读取全部文件内容。

## 5.3 文件写入
如果以 r+、w、w+、a、a+ 模式打开文件，则都可以写入。需要指出的是，当以 r+、w、w+ 模式打开文件时，文件指针位于文件开头处；当以 a、a+ 模式打开文件时，文件指针位于文件结尾处。<br>
另外，需要说明的是，当以 w 或 w+ 模式打开文件时，程序会立即清空文件的内容。<br>
**文件指针**用于标明文件读写的位置。假如把文件看成一个水流，文件中每个数据（以 b 模式打开，每个数据就是一个字节；以普通模式打开，每个数据就是一个字符）就相当于一个水滴，而文件指针就标明了文件将要读写哪个位置。<br>
文件对象提供了以下方法来操作文件指针：
- **seek(offset[, whence])**：该方法把文件指针移动到指定位置。当 whence 为 0 时（这是默认值），表明从文件开头开始计算，比如将 offset 设为 3，就是将文件指针移动到第 3 处；当 whence 为 1 时，表明从指针当前位置开始计算，比如文件指针当前在第 5 处，将 offset 设为 3，就是将文件指针移动到第 8 处；当 whence 为 2 时，表明从文件结尾开始计算，比如将 offset 设为 3，表明将文件指针移动到文件结尾倒数第 3 处。
- **tell()**：判断文件指针的位置。

文件对象提供的写文件的方法主要有两个：
- **write(str 或 bytes)**：输出字符串或字节串。只有以二进制模式（b 模式）打开的文件才能写入字节串。
- **writelines（可迭代对象）**：输出多个字符串或多个字节串。
## 5.4 excel及csv文件操作
python操作excel主要用到xlrd和xlwt这两个库，即xlrd是读excel，xlwt是写excel的库

每一个Excel数据文件从上至下分为三个层级的对象：<br>
**workbook**： 每一个Excel文件就是一个workbook。<br>
**sheet**： 每一个workbook中可以包含多个sheet，具体就对应Excel中我们在左下脚所看到的“sheet1”,“sheet2”等。<br>
**cell**： 每一个sheet就是我们通常所看到的一个表格，可以含有m行，n列，每个确定的行号，列号所对应的一个格子就是一个cell。<br>

    #打开excel文件
    data=xlrd.open_workbook('data.xlsx')     
    #获取第一张工作表（通过索引的方式）
    table=data.sheets()[0] 
    #data_list用来存放数据
    data_list=[]    
    #将table中第一行的数据读取并添加到data_list中
    data_list.extend(table.row_values(0))
    #打印出第一行的全部数据
    for item in data_list:
        print item

工作表也可以通过索引或者名字获得

    sheet1 = wb.sheet_by_index(0)#通过索引获取表格
    sheet2 = wb.sheet_by_name('年级')#通过名字获取表格
  
数据获取的格式有以下几种：

    cell_A1=table.row(0)[0].value
    #或者像下面这样
    cell_A1=table.cell(0,0).value
    #或者像下面这样通过列索引
    cell_A1=table.col(0)[0].value
    
读取合并单元格的方式可以通过merged_cells()，merged_cells返回的这四个参数的含义是：(row,row_range,col,col_range),其中[row,row_range)包括row,不包括row_range,col也是一样。<br>
写入合并单元格的方式可以通过write_merge
    
# 6. os模块
os 模块提供了大量操作文件和目录的函数, 与目录相关的函数如下：
- os.getcwd()：获取当前目录。
- os.chdir(path)：改变当前目录。
- os.fchdir(fd)：通过文件描述利改变当前目录。该函数与上一个函数的功能基本相似，只是该函数以文件描述符作为参数来代表目录。
- os.chroot(path)：改变当前进程的根目录。
- os.listdir(path)：返回 path 对应目录下的所有文件和子目录。
- os.mkdir(path[, mode])：创建 path 对应的目录，其中 mode 用于指定该目录的权限。该 mode参数代表一个 UNIX 风格的权限，比如 0o777 代表所有者可读/可写/可执行、组用户可读/可写/可执行、其他用户可读/可写/可执行。
- os.makedirs(path[, mode])：其作用类似于 mkdir()，但该函数的功能更加强大，它可以边归创建目录。比如要创建 abc/xyz/wawa 目录，如果在当前目录下没有 abc 目录，那么使用 mkdir() 函数就会报错，而使用 makedirs() 函数则会先创建 abc，然后在其中创建 xyz 子目录，最后在 xyz 子目录下创建 wawa 子目录。
- os.rmdir(path)：删除 path 对应的空目录。如果目录非空，则抛出一个 OSError 异常。程序可以先用 os.remove() 函数删除文件。
- os.removedirs(path)：边归删除目录。其功能类似于 rmdir()，但该函数可以递归删除 abc/xyz/wawa 目录，它会从 wawa 子目录开始删除，然后删除 xyz 子目录，最后删除 abc 目录。
- os.rename(src, dst)：重命名文件或目录，将 src 重名为 dst。
- os.renames(old, new)：对文件或目录进行递归重命名。其功能类似于 rename()，但该函数可以递归重命名 abc/xyz/wawa 目录，它会从 wawa 子目录开始重命名，然后重命名 xyz 子目录，最后重命名 abc 目录。
    
# 7. datetime模块
datatime模块重新封装了time模块，提供更多接口，提供的类有：date,time,datetime,timedelta,tzinfo。
## 1. date类
<br>date.max、date.min：date对象所能表示的最大、最小日期；
<br>date.resolution：date对象表示日期的最小单位。这里是天。
<br>date.today()：返回一个表示当前本地日期的date对象；
<br>date.fromtimestamp(timestamp)：根据给定的时间戮，返回一个date对象；
<br>
<br>d1 = date(2019,06,29)#date对象
<br>d1.year、date.month、date.day：年、月、日；
<br>d1.replace(year, month, day)：生成一个新的日期对象，用参数指定的年，月，日代替原有对象中的属性。（原有对象仍保持不变）
<br>d1.timetuple()：返回日期对应的time.struct_time对象；
<br>d1.weekday()：返回weekday，如果是星期一，返回0；如果是星期2，返回1，以此类推；
<br>d1.isoweekday()：返回weekday，如果是星期一，返回1；如果是星期2，返回2，以此类推；
<br>d1.isocalendar()：返回格式如(year，month，day)的元组；
<br>d1.isoformat()：返回格式如'YYYY-MM-DD’的字符串；
<br>d1.strftime(fmt)：和time模块format相同。
<br>
<br>## 2. time类
<br>time.min、time.max：time类所能表示的最小、最大时间。其中，time.min = time(0, 0, 0, 0)， time.max = time(23, 59, 59, 999999)；
<br>time.resolution：时间的最小单位，这里是1微秒；
<br>
<br>t1 = datetime.time(10,23,15)#time对象
<br>t1.hour、t1.minute、t1.second、t1.microsecond：时、分、秒、微秒；
<br>t1.tzinfo：时区信息；
<br>t1.replace([ hour[ , minute[ , second[ , microsecond[ , tzinfo] ] ] ] ] )：创建一个新的时间对象，用参数指定的时、分、秒、微秒代替原有对象中的属性（原有对象仍保持不变）；
<br>t1.isoformat()：返回型如"HH:MM:SS"格式的字符串表示；
<br>t1.strftime(fmt)：同time模块中的format；
<br>
<br>## 3. datetime类
<br>datetime.today()：返回一个表示当前本地时间的datetime对象；
<br>datetime.now([tz])：返回一个表示当前本地时间的datetime对象，如果提供了参数tz，则获取tz参数所指时区的本地时间；
<br>datetime.utcnow()：返回一个当前utc时间的datetime对象；#格林威治时间
<br>datetime.fromtimestamp(timestamp[, tz])：根据时间戮创建一个datetime对象，参数tz指定时区信息；
<br>datetime.utcfromtimestamp(timestamp)：根据时间戮创建一个datetime对象；
<br>datetime.combine(date, time)：根据date和time，创建一个datetime对象；
<br>datetime.strptime(date_string, format)：将格式字符串转换为datetime对象；
<br>
<br>dt=datetime.now()#datetime对象
<br>dt.year、month、day、hour、minute、second、microsecond、tzinfo：
<br>dt.date()：获取date对象；
<br>dt.time()：获取time对象；
<br>dt. replace ([ year[ , month[ , day[ , hour[ , minute[ , second[ , microsecond[ , tzinfo] ] ] ] ] ] ] ])：
<br>dt. timetuple ()
<br>dt. utctimetuple ()
<br>dt. toordinal ()
<br>dt. weekday ()
<br>dt. isocalendar ()
<br>dt. isoformat ([ sep] )
<br>dt. ctime ()：返回一个日期时间的C格式字符串，等效于time.ctime(time.mktime(dt.timetuple()))；
<br>dt. strftime (format)
<br>
