# python_note
学习Python的笔记集
# Python
# 基础操作，内置函数，数据结构，获取和改变工作路径，文件操作
# Pandas,time,tkinter,xlwings,
	数据分析
	界面GUI
	环境配置基础操作

# tkinter研究
	主背景框
		tk.Tk()
		tk.mainloop()
	部件
	'''状态栏、气泡等'''
		Label,Entry,Button,
		$ Label
			lab = tk.Label(root,text='')
		    lab.place(x=100,y=100)
		$ Entry
		$ Button
			but = tk.Button(root,text='按钮',command=def)
			but.place(x=100,y=100)
		$ Text
		$ Treeview
		$ Scrollbar
		$ 

# Python基础
	操作系统接口 import os
		os.getcwd()
		os.chdir('dir')
		os.system('Win-command')

		var1,var2 = var2,var1	交换变量值
	数值转换
		int()
		float()
		long()
		str()
	
	字符串 string
		string1+string2
		string*3
		len(string)
		string.split("",2)	string中以""分隔，拆分2次，默认以空格拆分
		','.join(string)	以','连接列表元素
		string.strip()	参数为需要去除的字符
		string.lstrip()
		string.rstrip()
		string.replace(" ",",")	" "替换为","
		string.lower()
		string.upper()
		string.capitalize()
		for word in string.split()
			word.capitalize()

		……ljust，rjust，center方法
		string.ljust(5,"*")	宽度5个字符，空白处以*填充
		str.zfill(5)	数值型字符串左侧以0填充位数
		str.format()
			eg:print('We are the {0:s} who say{1}'.format('knights','Ni'))
			大括号带索引，以format参数位置填充
			print({0[key]}.format(dict))
			print({key}.format(**dict))
		startwith,endwith
		isX

	
	列表 list
		l = [1,2,3]	方括号创建列表
		l[0:2]	列表切片左闭右开
		l[1:1]	切片插入元素
		len(l) l的元素数
		max(l)
		min(l)
		l.count(2)	列表内2出现的次数
		l[0]
		l[-1]
		l[0:2]
		l[:2]	
		l[:]	列表复制
		list1+list2
		2 in l 	检查2是否在列表l中	
		2 not in l 	检查2是否在列表l中	
		l.append(4)	l中追加元素4
		l[len(l):]=4	l中追加元素4
		l.extend(list)	追加一个列表list
		l.insert(i,x)	在指定位置插入元素，插到l[i]之前
		l.remove(4)	l中删除元素4
		l.pop()	l中删除最后一个元素
		l.index(x)	返回列表中第一个值为x的元素索引
		l.count(x)	返回列表中元素x出现的次数
		l.reverse()	列表l元素原地反转，改变原值
		l.sort()	列表l元素原地排序，改变原值
		del l[0]	切片删除
		$二维列表排序		副本排序，不改变原值
		b = [[1,2,3,4],[4,3,2,1],[2,4,1,3]]
		sorted(b,key=lambda index_value:index_value[3])
		$from operator import itemgetter
		sort(b,key=itemgetter(3,0))	先按索引3，再按索引0为列表排序
		列表生成式：[]=[x**2 for x in range(10)]

	元组 tuple
		t = ('x','y','z')	圆括号创建元组/元组封装
		var1,var2,var3 = t 	将元组t解包给三个变量
		tuple(list1)	将list1转为元组
		list(tuple1)	将tuple1转为列表

	集合 set
		set()	创建空集合
		basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
		a = set('abracadabra')
		a = {x for x in 'abracadabra' if x not in 'abc'}
		?union,intersection,difference,sysmmetric difference
		set1.intersection(set2)/set1&set2
		set1.union(set2)/set1|set2
		set1.difference(set2)/set1-set2
		set1.symmetric_difference(set2)/set1^set2



	字典 dictionary
		d = {'one':'1','two':'2','three':'3'}
		len(d)	字典d中健-值对个数
		d['two']	根据键名返回值2
		d.copy 	建立字典副本
		d.keys()
		d.values()
		d.items()
		'one' in d 	判别one是否是字典d中的键
		d.get('three')	返回three对应的值
		d.get('four','Not in dict')	如果字典中找不到值，返回第二个参数
		？字典排序
			sorted(d.items(),key=lambda item:item[0])
			sorted(d.keys())
		字典推导式：{x:x**2 for x in (2,4,6)}
		for k,v in d.items()	输出键值对
		zip?打包字典
		vars()?

	控制流
		range(from,to,step)	生成序列
		?enumerate()
		IF语句
		if cond:
			expr
		elif
			expr
		else
			expr

		FOR循环
		for i in range:
			expr

		i for i in range if cond
		列表生成式：
		[row for row in list1 if row[2]>5]	保留二维列表中第三个元素大于5的列表
		集合生成式：
		{x for x in list2}
		set(list2)
		字典生成式：
		{key:value for key,value in d.items() if cond}
			从字典中选出符合条件的键-值对

		WHILE循环
			while cond:
				expr

		函数
		def function(arg):
			body

		lambda a,b:a+b 	求和函数

		TRY-EXPECT语句

	读取文本文件

# 文件读写
	f = open(filename,mode)
		'r'	只读，文件需存在
		'rb' 只写，文件需存在
		'r+' 读，覆盖写，文件需存在
		'rb+' 非文本文件打开，文件需存在
		'w'	只写，覆盖原文件，创建新文件
		'wb' 二进制打开只写，覆盖原文件，创建新文件
		'w+' 清空原文件，读写
		'wb+' 非文本文件
		'a'	追加方式打开
		'ab'	二进制格式打开文件
		'a+' 读写，追加，创建新文件
		'ab+' 二进制打开，追加，创建新文件
	f.seek(6)	移动文件指针到新位置
	f.read(9)	读取前9个字符
	f.readline()	读取一行
	f.readlines()	返回以行为元素的列表，读取全部行
	for line in f:
		print(line,end='')	遍历文件对象操作
	f.write(string)	将字符串写入文件  **返回写入字符长度
	f.tell()
	f.seek(5,2)	查找特定位置，字符数的字符串
	with open(filename,mode) as f:	with语句，使用完成后自动关闭对象

# 文件夹操作 os和os.path,shutil
	os.name 	返回操作系统名称
	os.linesep 	换行符
	os.sep 	当前路径分隔符
	os.getcwd()
	os.listdir(path)	返回path中文件和文件夹信息
	os.mkdir()	新建文件夹
	os.mkdirs()	新建多级文件夹
	os.rmdir()
	os.removedirs()
	os.chdir(path)
	os.walk()	遍历目录树

	os.path.abspath(path)
	os.path.exists(path)
	os.path.join(path,name)
	os.path.splitext()	分离文件名和拓展名
	os.path.basename(path)
	os.path.dirname(path)
	os.path.isdir()

	shutil
	复制，移动，重命名，删除，遍历
	shutil.copy(source,destination)
	shutil.copytree(source,destination) 若destination不存在则新建
	shutil.move(source,destination)	destination必须存在
	



# 读取CSV文件，CSV模块 import csv
		with open(file,'r',newline='') as file_open:




# pandas模块
