

```python
print(7/3)
```

    2.3333333333333335



```python
print(7//3)
```

    2



```python
print(7%3)
```

    1



```python
print(7**2)
```

    49



```python
myList = [0]*6
myList
```




    [0, 0, 0, 0, 0, 0]




```python
myList1 = [1, 2, 3, 4]
A = [myList1]*3 #注意此处有无[]的区别
print(A)
```

    [[1, 2, 3, 4], [1, 2, 3, 4], [1, 2, 3, 4]]



```python
myList1[2] = 45
print(A)
```

    [[1, 2, 45, 4], [1, 2, 45, 4], [1, 2, 45, 4]]



```python
2 in A
```




    False




```python
[1, 2, 45, 4] in A
```




    True




```python
B = ['HI']
C = A + B
C
```




    [[1, 2, 45, 4], [1, 2, 45, 4], [1, 2, 45, 4], 'HI']




```python
len(C)
```




    4




```python
C[1:3]
```




    [[1, 2, 45, 4], [1, 2, 45, 4]]




```python
myList2 = [1024, 3, True, 6.5] 
myList2.append(False) 
print(myList2) 
```

    [1024, 3, True, 6.5, False]



```python
myList2.insert(2,4.5)
print(myList2) 
```

    [1024, 3, 4.5, True, 6.5, False]



```python
print(myList2.pop()) 
```

    False



```python
print(myList2) 
```

    [1024, 3, 4.5, True, 6.5]



```python
print(myList2.pop(1)) 
print(myList2) 
```

    3
    [1024, 4.5, True, 6.5]



```python
print(myList2.pop(2)) 
print(myList2) 
```

    True
    [1024, 4.5, 6.5]



```python
myList2.sort()
print(myList2)
```

    [4.5, 6.5, 1024]



```python
myList2.reverse()
print(myList2)
```

    [1024, 6.5, 4.5]



```python
print(myList2.count(6.5))
```

    1



```python
print(myList2.index(4.5))
```

    2



```python
myList2.remove(6.5)
print(myList2)
```

    [1024, 4.5]



```python
(54).__add__(21)
```




    75



字符串


```python
myName = "David" 
myName * 2

```




    'DavidDavid'




```python
myName.upper()
```




    'DAVID'




```python
myName.lower()
```




    'david'



## 集合


```python
set(range(7))

```




    {0, 1, 2, 3, 4, 5, 6}




```python
mySet = {3, 6, 'cat', 4.5, False}
mySet
```




    {3, 4.5, 6, False, 'cat'}




```python
len(mySet)
```




    5




```python
3 in mySet
```




    True




```python
yourSet = {99, 3, 100}
mySet.union(yourSet)
```




    {100, 3, 4.5, 6, 99, False, 'cat'}




```python
mySet|yourSet
```




    {100, 3, 4.5, 6, 99, False, 'cat'}




```python
mySet.intersection(yourSet)
```




    {3}




```python
mySet&yourSet
```




    {3}




```python
mySet.difference(yourSet)
```




    {4.5, 6, False, 'cat'}




```python
mySet - yourSet
```




    {4.5, 6, False, 'cat'}




```python
{3, 100}.issubset(yourSet)
```




    True




```python
{3, 100}<=yourSet
```




    True




```python
mySet.add("house") #remove,pop,clear
mySet
```




    {3, 4.5, 6, False, 'cat', 'house'}




```python
mySet.clear()
mySet
```




    set()



## dict


```python
# clear
d = {}
d['name'] = 'marry'
d['age'] = '12'
d
```




    {'age': '12', 'name': 'marry'}




```python
returned_value = d.clear()
d
```




    {}




```python
returned_value = d.clear()#clear就地执行，什么都不返回
print(returned_value)
```

    None



```python
x = {}
y = x
x['key'] = 'value'
y
```




    {'key': 'value'}




```python
x = {} #将空字典赋给x来“清空”它，y仍然指向原来的字典，不受影响。
y
```




    {'key': 'value'}




```python
m = {}
n = m
m['key'] = 'value'
n
```




    {'key': 'value'}




```python
m.clear()#clear删除原来字典的所有元素
n
```




    {}




```python
# copy
x = {'username':'admin','machines':['foo','bar','baz']}
y = x.copy()
y['username'] = 'shi'
y['machines'].remove('bar')
y
```




    {'machines': ['foo', 'baz'], 'username': 'shi'}




```python
x # 替换副本中的值，原件x不受影响；修改副本（就地修改）原件变化
```




    {'machines': ['foo', 'baz'], 'username': 'admin'}




```python
from copy import deepcopy
d = {}
d['names'] = ['xiaom','xiaol']
c = d.copy()
dc = deepcopy(d)
```


```python
d['names'].append('xiaoh')
```


```python
print("c is:",c)
print("dc is:",dc)
```

    c is: {'names': ['xiaom', 'xiaol', 'xiaoh']}
    dc is: {'names': ['xiaom', 'xiaol']}


## 类和实例


```python
# 类是抽象的模板，比如Student类，
# 而实例是根据类创建出来的一个个具体的“对象”，
# 每个对象都拥有相同的方法，但各自的数据可能不同
```


```python
# 由于类可以起到模板的作用，因此，可以在创建实例的时候，
# 把一些我们认为必须绑定的属性强制填写进去。
# 通过定义一个特殊的__init__方法，在创建实例的时候，就把name，score等属性绑上去：
class Student(object):
    def __init__(self, name, score):#__init__方法的第一个参数永远是self，表示创建的实例本身
        self.name = name
        self.score = score
```


```python
bart = Student('Bart Simpson', 59)
```


```python
bart
```




    <__main__.Student at 0x13b569678d0>




```python
bart.name
```




    'Bart Simpson'




```python
bart.score
```




    59




```python
# 数据封装:面向对象编程的一个重要特点就是数据封装。
# 在上面的Student类中，每个实例就拥有各自的name和score这些数据。
# 我们可以通过函数来访问这些数据，比如打印一个学生的成绩：
```

##  通过类来创建抽象数据类型


```python
class Fraction:
    def __init__(self,top,bottom):#self 是一个特殊的参数，用来作为参考返回对象本身
        self.num = top
        self.den = bottom
```


```python
myFraction = Fraction(3,5)
print(myFraction)
#fraction 对象，myf，不知道如何回应这一打印要求。
#打印功能要求对象转换成字符串以至于该 字符串可以输入输出。
#myf 唯一的选择是显示该变量中存储的实际引用（本身的地址）。
```

    <__main__.Fraction object at 0x00000222546CF630>



```python
class Fraction1:
    def __init__(self,top,bottom):
        self.num = top
        self.den = bottom
    def show(self):
        print(self.num,"/",self.den) 
myf1 = Fraction1(1,5) 
myf1.show() 
```

    1 / 5



```python
print(myf1)
```

    <__main__.Fraction1 object at 0x00000222546E7B70>



```python
# __str__是一种方法来将对象转为字符串,默认实现是返回我们已经看到的地址的字符串。
# 我们简单地定义一个方法，名称为__str__并给它一个新的实现.
class Fraction2:
    def __init__(self,top,bottom):
        self.num = top
        self.den = bottom
    def __str__(self):
        return str(self.num)+"/"+str(self.den) 
myf2 = Fraction2(2,5) 
print(myf2)
```

    2/5



```python
print('I ate',myf2,'of the pizza')
```

    I ate 2/5 of the pizza



```python
myf2.__str__()
```




    '2/5'




```python
str(myf2)
```




    '2/5'




```python
# 我们希望能创建两个分数对象然后他们加在一起使用标准的“+”符号。
#在这一点上，如果我们试图直 接相加两个分数，则会得到如下： 
f1 = Fraction2(1,4)
f2 = Fraction2(1,2)
f1+f2
```


    ---------------------------------------------------------------------------
    
    TypeError                                 Traceback (most recent call last)
    
    <ipython-input-61-441072e758b2> in <module>()
          3 f1 = Fraction2(1,4)
          4 f2 = Fraction2(1,2)
    ----> 5 f1+f2


    TypeError: unsupported operand type(s) for +: 'Fraction2' and 'Fraction2'



```python
#以通过提供 Fraction 类重写方法解决这个问题。在 Python 中，这种方法被称为 __add__，
#它需要两个参数。第一，self，这个总是需要的，第二是在另一个被操作数的表达。
class Fraction3:
    def __init__(self,top,bottom):
        self.num = top
        self.den = bottom
    def __str__(self):
        return str(self.num)+"/"+str(self.den) 
    def __add__(self,otherfraction): 
        newnum = self.num*otherfraction.den + self.den*otherfraction.num 
        newden = self.den * otherfraction.den 
        return Fraction3(newnum,newden) 
f1=Fraction3(1,4) 
f2=Fraction3(1,2) 
f3=f1+f2 
print(f3)
```

    6/8



```python
#方法“__add__”达到了目的，但并不完美。6/8 的确是对的，但最好的答案应该是 3/4。
#为保证运算结果为最简分数，我们需要一个辅助函数来识别并化简分数。
# 这个函数需要能够找到分子分母的最大公因数，
# 然后将分子分母同时除以最大公因数，得到最简分数答案。 
#最著名的寻找最大公因数的方法是欧几里得算法
```

## 二、算法分析

## 三、基本数据结构类型

## 常用内建属性介绍：__str__,__repr__


```python
class Student(object):
    def __init__(self,name):
        self.name = name
s1 = Student("Jack")
s11 = [1,"aa","bb"]
print(s1)
print(s11)
```

    <__main__.Student object at 0x0000013B56A1F898>
    [1, 'aa', 'bb']


### 1.__str__的功能和方法：


```python
# 1.__str__功能：将实例对象按照自定义的格式用字符串的形式显示出来，提高可读性。
# 2.实例化的对象在打印或时会默认调用__str__方法，如果类没有重写这个方法，
# 默认调用父类object的__str__方法。
# 3.object的__str__方法内部是pass，所以打印的是内存地址。
# 如果当前类重写了这个方法，会自动调用重写后的方法。

class Student(object):
    def __init__(self,name,age):
        self.name = name
        self.age = age
    def __str__(self):
        print("我要可视化输出实例内容啦")
        return "Student(%s年龄是%d)"%(self.name,self.age)
s2 = Student("Jack",29)
print(s2)
```

    我要可视化输出实例内容啦
    Student(Jack年龄是29)


2.__repr__的功能与用法
  1.__repr__如果用IDE软件操作，功能与__str__完全一样，都是实例可视化显示
  2.开发中如果用户需要可视化实例内容，只需要重写__str__或者__repr__方法之一即可。
     如果两个都有的话，默认调用__str__.
  3.两者的区别就是使用命令行操作：
     3.1__str__重写后，如果直接实例stu回车的话，显示的是stu实例在内存中的地址，
        跟print(stu)不一样。
     3.2__repr__重写后，如果直接实例stu回车的话，效果跟使用print(stu)一样，
        返回内容，不是内存地址。       
4.__str__与__repr__两个函数同时存在，优先执行__str__函数。


```python
class Student(object):
    def __init__(self,name,age):
        self.name = name
        self.age = age
        
    def __str__(self):
        print("我是str")
        return "Student(%s的年龄是%d)"%(self.name,self.age)
    def __repr__(self):
        print("我是repr")
        return "Student11111(%s,%d)" % (self.name, self.age)
 
s3 = Student("JACK",29)
print(s3)
 
```

    我是str
    Student(JACK的年龄是29)



```python
# 栈 
#项添加和删除的一端称为“顶”
class Stack(object):
     # 初始化栈为空列表
    def __init__(self):
        self.items = []
    def is_empty(self):  # 判断栈是否为空，返回布尔值
        return self.items == []
      
    def peek(self): # 返回栈顶元素
        return self.items[len(self.items) - 1] 
    
    def size(self): # 返回栈的大小 
        return len(self.items) 
    
    def push(self, item): # 把新的元素堆进栈里面（压栈，入栈，进栈……） 
        self.items.append(item) 
        
    def pop(self): # 把栈顶元素丢出去（出栈……） 
        return self.items.pop()
    
    def __repr__(self): 
        try:
            return self.items.__repr__()
        except:
            pass
            
#     def show(self):  ## 这个函数名是任意起的
#         try:
#             return self.items.__repr__()
#         except:
#             pass

```


```python
s = Stack()
s.is_empty()
```




    True




```python
s.push(4)
s.push("dog")
```


```python
s.size()
```




    2




```python
print(s)
```

    [4, 'dog']



```python
s.peek() 
```




    'dog'




```python
s.push("Ture")
```


```python
s.push(8.4)
```


```python
s
```




    [4, 'dog', 'Ture', 8.4]




```python
s.pop()
```




    8.4




```python
s.pop()
```




    'Ture'




```python
s
```




    [4, 'dog']



### 队列
###队列（Queue）是一系列有顺序的元素的集合，新元素的加入在队列的一端，这一端叫做“队尾” ###（rear），已有元素的移除发生在队列的另一端，叫做“队首”（front）。当一个元素被加入到###队列之 后，它就从队尾开始向队首前进，直到它成为下一个即将被移出队列的元素。 


```python
# 需要决定列表的哪一端做队尾，哪一端用来做队首。
# 下面的一段代码设定队列的队尾在列表的 0 位置
class Queue():
    def __init__(self):
        self.items = []
        
    def isEmpty(self):
        return self.items == []
    
    def enqueue(self,item): #着 enqueue 的复杂度是 O(n)
        self.items.insert(0,item)
    def dequeue(self):# dequeue 的复杂度是 O(1)。
        return self.items.pop()
        
    def size(self):
        return len(self.items)
    
    def __repr__(self):
        return self.items.__repr__()
```


```python
q = Queue()
```


```python
q.enqueue(4)
q
```




    [4]




```python
q.enqueue("dog")
q
```




    ['dog', 4]




```python
q.enqueue(True)
q
```




    [True, 'dog', 4]




```python
q.size()
```




    3




```python
q.dequeue()
```




    4




```python
# 队列运作方式一个典型实例就是模拟出一个需要运用到先进先出（FIFO）数据管理方式的真实情景。
# 热土豆的儿童游戏：孩子们围成一个圆圈并以最快的速度接连传递物品，在游戏的一个特定时刻停止
# 传递，这时手中拿着物品的小孩就离开圆圈，游戏进行至只剩下一个小孩。
#注意：1.第一个拿着土豆的孩子为0，接下来拿到土豆的计数为1；
# 2.这个例子中给出的传土豆数要大于列表中人名的个数；
class Queue():
    def __init__(self):
        self.items = []       
    def isEmpty(self):
        return self.items == []    
    def enqueue(self,item): #着 enqueue 的复杂度是 O(n)
        self.items.insert(0,item)
    def dequeue(self):# dequeue 的复杂度是 O(1)。
        return self.items.pop()        
    def size(self):
        return len(self.items)    
    def __repr__(self):
        return self.items.__repr__()
 
def hotPotato(namelist, num): 
    simqueue = Queue() 
    for name in namelist: 
        simqueue.enqueue(name) 
        print("test1:simqueue is ", simqueue)
 
    while simqueue.size() > 1: 
        for i in range(num): 
            simqueue.enqueue(simqueue.dequeue()) 
 
        a = simqueue.dequeue() 
        print("test2:dequeue item is:" ,a)
 
    return simqueue.dequeue() #最后列队里面就剩下一个人了

print(hotPotato(["Bill","David","Susan","Jane","Kent","Brad"],7)) 
```

    test1:simqueue is  ['Bill']
    test1:simqueue is  ['David', 'Bill']
    test1:simqueue is  ['Susan', 'David', 'Bill']
    test1:simqueue is  ['Jane', 'Susan', 'David', 'Bill']
    test1:simqueue is  ['Kent', 'Jane', 'Susan', 'David', 'Bill']
    test1:simqueue is  ['Brad', 'Kent', 'Jane', 'Susan', 'David', 'Bill']
    test2:dequeue item is: David
    test2:dequeue item is: Kent
    test2:dequeue item is: Jane
    test2:dequeue item is: Bill
    test2:dequeue item is: Brad
    Susan


## 双端队列（deque 或 double-ended queue）


```python
# Deque假设尾队尾在列表的 0 位置
class Deque():
    def __init__(self):
        self.items = []
    def isEmpty(self):
        return self.items == []
    
    def size(self):
        return len(self.items)
    
    def addRear(self,item):
        self.items.insert(0,item)
    def addFront(self,item):
        self.items.append(item)
    
    def removeRear(self):                # 注意此处self
        return self.items.pop(0)   # 注意此处return     
    def removeFront(self):# 注意此处self
        return self.items.pop()# 注意此处return 
        
    def __repr__(self):
        return self.items.__repr__()
```


```python
d = Deque()
```


```python
d.isEmpty()
```




    True




```python
d.addRear(4)
```


```python
d
```




    [4]




```python
d.addRear('dog')
d
```




    ['dog', 4]




```python
d.addFront('cat')
d
```




    ['dog', 4, 'cat']




```python
d.addFront(True)
d
```




    ['dog', 4, 'cat', True]




```python
d.size()
```




    4




```python
d.isEmpty()
```




    False




```python
d.addRear(8.4)
d
```




    [8.4, 'dog', 4, 'cat', True]




```python
d.removeRear()
d
```




    ['dog', 4, 'cat', True]




```python
d.removeFront()
d
```




    ['dog', 4, 'cat']




```python
## 例子：判断回文数
class Deque():
    def __init__(self):
        self.items = []
    def isEmpty(self):
        return self.items == []    
    def size(self):
        return len(self.items)    
    def addRear(self,item):
        self.items.insert(0,item)
    def addFront(self,item):
        self.items.append(item)   
    def removeRear(self):                
        return self.items.pop(0)   
    def removeFront(self):
        return self.items.pop()        
    def __repr__(self):
        return self.items.__repr__()
    
def palchecker(aString): 
    chardeque = Deque() 
    for ch in aString:
        chardeque.addRear(ch)
    stillEqual = True 
    while  chardeque.size() > 1 and stillEqual:
        first = chardeque.removeFront() 
        last = chardeque.removeRear()
        if first != last:
            stillEqual = False
    if stillEqual:
        return   "%s is a palindrome" %aString # 注意此处格式
    else:
        return  "%s isn't a palindrome" %aString
            
        
```


```python
print(palchecker("lsdkjfskf"))
```

    lsdkjfskf isn't a palindrome


## 采用链表实现无序列表 


```python
# 1 Node类
# 节点（Node）是链表实现的基本构造，由列表项（item，数据字段）和对下一个节点的引用组成。
# Node 类包括访问，修改数据和访问下一个引用等常用方法。类的代码如下：
class Node():
    def __init__(self,initdata):
        self.data = initdata
        self.next = None 
#         在构造器中，一个节点的对下一节点引用的初始赋值是 None。
#         因为这有时被称为把节 点“接地”（grounding），
#         我们在图中将使用标准化的“接地”标志来表示一个值为 None 的引 用。
#         用 None 来作为你在初始化时对下一个节点的引用是一个极妙的主意。

    def getData(self):
        return self.data
    def getNext(self):
        return self.next
    def setData(self,newdata):
        self.data = newdata
    def setNext(self,newnext):
        self.next = newnext
        
    
```


```python
# 2 Unordered List 类
# 头插法
# 如上所述，无序列表将从一组节点构建，每个节点通过显式引用链接到下一个节点。
# 只要我们知道在哪里找到第一个节点（包含第一个项），之后的每个项可以通过
# 连续跟随下一个链接找到。考虑到这一点，UnorderedList 类必须保持对第一个节点的引用，
# 如下图所示，实现代码如下：
class UnorderedList():
    def __init__(self):
        self.head = None
    def isEmpty(self):
        return self.head == None
    
        
## 点睛：1.变量名即为地址
## 2.首次temp.setNext(self.head)里self.head为None
    def add(self,item):
        temp = Node(item) #创建一个新的节点，item作为节点的数据
        temp.setNext(self.head)#更新新节点的下一个引用，以引用旧链表的第一个节点
        self.head = temp#赋值语句设置列表的头
        
    def __repr__(self):
        l = []
        h = self.head
        while h != None:
            l.append(h.data)
            h = h.next
        return str(l)
       
# 接下来我们所要实现的方法：求元素个数（size）、查找（search）和移除（remove），
# 全部基于一个叫做链表的遍历（traversal）的操作的。
# 遍历指的是有序地访问每一个节点的过程。为了做到，可用一个外部引用，
# 它最开始指向列表的第一个节点。每当访问一个节点时，
# 通过“侧向移动”（traversing）到下一个引用的方式，将外部引用移动到下一个节点。
    def size(self):
        current = self.head
        count = 0
        while current != None:
            count = count + 1
            current = current.getNext
        return count
    def search(self,item):
        current = self.head
        found = False
        while current!=None and not found:
            if current.getData == item:
                found = True
            else:
                current = current.getNext()
        return found
    def remove(self,item):#假设待移除的元素一定存在
        current = self.head
        previous = None
        found = False
        while not found:
            if current.getData() == item:
                found = True
            else:#如果没有找到元素，previous和current必须同时向后移动一个节点
                previous = current
                current = current.getNext()
        if previous == None:#若要删除是链表中第一个项，链表的 head 需要改变
                self.head = current.getNext()
        else:
                previous.setNext(current.getNext())
        

```


```python
mylist = UnorderedList()
```


```python
# 链表结构只为我们提供了一个入口点，即链表的头部。
# 所有其他节点只能通过访问第一个节点，然后跟随下一个链接到达。
# 这意味着添加新节点的最简单的地方就在链表的头部。 
# 换句话说，我们将新项作为链表的第一项，现有项将需要链接到这个新项后。
```


```python
mylist.add(31)
```


```python
mylist.add(77) 
mylist.add(17) 
mylist.add(93) 
mylist.add(26) 
mylist.add(54) 
 
```


```python
mylist.remove(17)
print(mylist)
```

    [54, 26, 93, 77, 31]



```python
mylist.remove(54)
print(mylist)
```

    [26, 93, 77, 31]



```python
mylist.remove(31)
print(mylist)
```

    [26, 93, 77]



```python
# 剩下的方法:追加（append），插入（insert），索引（index），弹出（pop）,
# 都将作为你的 练习。记住任何一个操作中都要同时考虑
# 对象在列表头部和其他位置这两种情况。
# 同样，插入、索 引、弹出需要我们给列表中的位置命名。
# 我们假定列表中位置的名称是从 0 开始的整数。 
```

# 抽象数据类型：有序列表 


```python
# 有序列表的结构是一个数据的集合体，在集合体中，每个元素相对其他元素
# 有一个基于元素的某些基本性质的位置。
# 假设已在列表元素中定义了一个有意义的比较大小的操作，则排序通常是升序或降序。
```


```python
class Node():
    def __init__(self,initdata):
        self.data = initdata
        self.next = None 
    def getData(self):
        return self.data
    def getNext(self):
        return self.next
    def setData(self,newdata):
        self.data = newdata
    def setNext(self,newnext):
        self.next = newnext
        
class orderedList():
    def __init__(self):        
        self.head = None
    def isEmpty(self):
        return self.head == None
    
        
    def __repr__(self):
        l = []
        h = self.head
        while h != None:
            l.append(h.data)
            h = h.next
        return str(l)
    
    def add(self,item):
        previous = None
        current = self.head
        stop = False
        while current != None and not stop:
            if current.getData() > item:
                stop = True
            else:
                previous = current
                current = current.getNext()
        temp = Node(item)
        if previous == None: 
            #别人此处的代码：temp.set_next(self.head) self.head = temp
            self.head = temp
            current = temp.getNext()
            previous = self.head
        else:
            temp.setNext(current)
            previous.setNext(temp)
    
            
            
```


```python
myorderedlist = orderedList()
myorderedlist.add(17) 
```


```python
print(myorderedlist)
```

    [17]



```python
myorderedlist.add(54) 
print(myorderedlist)
```

    [17, 54]



```python
myorderedlist.add(26) 
print(myorderedlist)
```

    [17, 26, 54]



```python
myorderedlist.add(93) 
print(myorderedlist)
```

    [17, 26, 54, 93]


# 四 、递归


```python
# 递归算法必须有个基本结束条件 
# 递归算法必须改变自己的状态并向基本结束条件演进 
# 递归算法必须递归地调用自身 
```

### 将整数转化成任意进制表示的字符串形式 
1）将原始整数分解为一连串的单个数字。 
2）通过在字符序列中检索将单个数字转换成字符串。 
3）将这些单个数字的字符串连接起来，形成最终的结果。 


```python
def to_str(n,base):
    convert_string = "0123456789ABCDEF"
    if n < base:
        return convert_string[n]
    else:
        return to_str(n//base,base)+convert_string[n%base]
print(to_str(765,10))
type(to_str(765,10))
```

    765





    str



## 4.3  栈帧：实现递归 


```python
class Stack(object):
     # 初始化栈为空列表
    def __init__(self):
        self.items = []
    def is_empty(self):  # 判断栈是否为空，返回布尔值
        return self.items == []
      
    def peek(self): # 返回栈顶元素
        return self.items[len(self.items) - 1] 
    
    def size(self): # 返回栈的大小 
        return len(self.items) 
    
    def push(self, item): # 把新的元素堆进栈里面（压栈，入栈，进栈……） 
        self.items.append(item) 
        
    def pop(self): # 把栈顶元素丢出去（出栈……） 
        return self.items.pop()
    
    def __repr__(self): 
        try:
            return self.items.__repr__()
        except:
            pass
        
r_stack = Stack()
def to_str(n,base):
    convert_string = "0123456789ABCDEF"
    while n > 0:
        if n < base:
            r_stack.push(convert_string[n])
        else:
            r_stack.push(convert_string[n%base])
        n = n//base
    res = ""
    while not r_stack.is_empty():
        res = res + str(r_stack.pop())
    return res
print(to_str(1453,16))


```

    5AD


### 4.4 图示递归


```python
# 用海龟画一个递归螺线
import turtle

myTurtle = turtle.Turtle()
myWin = turtle.Screen()

def drawSpiral(myTurtle,lineLen):
    if lineLen > 0:
        myTurtle.forward(lineLen)        
    myTurtle.right(90)
    drawSpiral(myTurtle,lineLen-5)
    
drawSpiral(myTurtle,100)
myWin.exitonclick()#将乌龟至于待机状态，等单击窗口时，页面才会清空，然后程序退出

```


    ---------------------------------------------------------------------------
    
    Terminator                                Traceback (most recent call last)
    
    <ipython-input-3-f06288570831> in <module>()
         11     drawSpiral(myTurtle,lineLen-5)
         12 
    ---> 13 drawSpiral(myTurtle,100)
         14 myWin.exitonclick()#将乌龟至于待机状态，等单击窗口时，页面才会清空，然后程序退出


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          9         myTurtle.forward(lineLen)
         10     myTurtle.right(90)
    ---> 11     drawSpiral(myTurtle,lineLen-5)
         12 
         13 drawSpiral(myTurtle,100)


    <ipython-input-3-f06288570831> in drawSpiral(myTurtle, lineLen)
          8     if lineLen > 0:
          9         myTurtle.forward(lineLen)
    ---> 10     myTurtle.right(90)
         11     drawSpiral(myTurtle,lineLen-5)
         12 


    F:\anaconda\lib\turtle.py in right(self, angle)
       1676         337.0
       1677         """
    -> 1678         self._rotate(-angle)
       1679 
       1680     def left(self, angle):


    F:\anaconda\lib\turtle.py in _rotate(self, angle)
       3274             for _ in range(steps):
       3275                 self._orient = self._orient.rotate(delta)
    -> 3276                 self._update()
       3277         self._orient = neworient
       3278         self._update()


    F:\anaconda\lib\turtle.py in _update(self)
       2658             return
       2659         elif screen._tracing == 1:
    -> 2660             self._update_data()
       2661             self._drawturtle()
       2662             screen._update()                  # TurtleScreenBase


    F:\anaconda\lib\turtle.py in _update_data(self)
       2644 
       2645     def _update_data(self):
    -> 2646         self.screen._incrementudc()
       2647         if self.screen._updatecounter != 0:
       2648             return


    F:\anaconda\lib\turtle.py in _incrementudc(self)
       1290         if not TurtleScreen._RUNNING:
       1291             TurtleScreen._RUNNING = True
    -> 1292             raise Terminator
       1293         if self._tracing > 0:
       1294             self._updatecounter += 1


    Terminator: 


# 五、排序与搜索


```python
#一个无序表的顺序排序 
def sequentialSearch(alist,item):
    pos = 0
    found = False
    while pos < len(alist) and not found:
        if alist[pos] == item:
            found = True
        else:
            pos = pos + 1
    return found
testlist = [1,2,32,8,17,19,42,13,0]
print(sequentialSearch(testlist,3))
print(sequentialSearch(testlist,13))
```

    False
    True



```python
#一个有序列表的顺序搜索
def orderedSequentialSearch(alist,item):
    pos = 0
    found = False
    stop = False
    while pos < len(alist) and not found and not stop:
        if alist[pos] == item:
            found = True
        else:
            if alist[pos] > item:
                print("stop")
                stop = True
            else:
                pos = pos + 1
    return found
testlist = [0,1,2,8,13,17,19,32,42]
print(orderedSequentialSearch(testlist,13))
print(orderedSequentialSearch(testlist,17))
```

    True
    True



```python
# 二分搜索--递归版本
def binarySearch(alist, item): 
    if  len(alist) == 0 : 
        return  False  
    else: 
        midpoint = len(alist)//2 
        if  alist[midpoint] == item: 
            return True 
        else: 
            if  item < alist[midpoint]: 
                return binarySearch (alist[:midpoint],item) 
            else: 
                return binarySearch (alist[midpoint+1:],item) 
testlist = [0, 1, 2, 8, 13, 17, 19, 32, 42,] 
print(binarySearch(testlist, 3)) 
print(binarySearch(testlist, 13))
```

# 散列表


```python
ord("a")
```




    97




```python
ord("A")
```




    65




```python
# 用ASCII数值散列一个字符串
def hash(astring,tablesize):
    sum = 0
    for pos in range(len(astring)):
        sum = sum + ord(astring[pos])       
    return sum % tablesize
hash("cat",11)
```




    4




```python
# 用ASCII数值散列一个字符串，权重因子
def hash(astring,tablesize):
    sum = 0
    weight = 0
    for pos in range(len(astring)):
        weight = weight + 1
        sum = sum + weight*ord(astring[pos])       
    return sum % tablesize
hash("cat",11)
```




    3




```python
class HashTable:
    def __init__(self):
        self.size = 11 # 槽的个数为11，序号从0开始，到10
        self.slots = [None]*self.size # 列表：self.slots槽，存储密钥
        self.data = [None]*self.size # 列表：self.data存储数据值
    def put(self,key,data):
        hashvalue = self.hashfunction(key,len(self.slots))

        if self.slots[hashvalue] == None:
            self.slots[hashvalue] = key
            self.data[hashvalue] = data
        else:
            if self.slots[hashvalue] == key:
                self.data[hashvalue] = data  #replace
            else:
                nextslot = self.rehash(hashvalue,len(self.slots))
                while self.slots[nextslot] != None and self.slots[nextslot] != key:                          
                    nextslot = self.rehash(nextslot,len(self.slots))

                if self.slots[nextslot] == None:
                    self.slots[nextslot]=key
                    self.data[nextslot]=data
                else:
                    self.data[nextslot] = data #replace

    def hashfunction(self,key,size):
             return key%size

    def rehash(self,oldhash,size):
            return (oldhash+1)%size
        
    def get(self,key):
        startslot = self.hashfunction(key,len(self.slots))

        data = None
        stop = False
        found = False
        position = startslot
        while self.slots[position] != None and not found and not stop:
            if self.slots[position] == key:
                found = True
                data = self.data[position]
            else:
                position=self.rehash(position,len(self.slots))
                if position == startslot:
                    stop = True
        return data

    def __getitem__(self,key):
        return self.get(key)

    def __setitem__(self,key,data):
        self.put(key,data)
```


```python
H = HashTable()
```


```python
H[54]="cat"
H[26]="dog"
H[93]="lion"
H[17]="tiger"
H[77]="bird"
H[31]="cow"
H[44]="goat"
H[55]="pig"
H[20]="chicken"
```


```python
H.slots
```




    [77, 44, 55, 20, 26, 93, 17, None, None, 31, 54]




```python
H.data
```




    ['bird',
     'goat',
     'pig',
     'chicken',
     'dog',
     'lion',
     'tiger',
     None,
     None,
     'cow',
     'cat']




```python
H[20]
```




    'chicken'




```python
H[20] = "goudan"
H[20]
```




    'goudan'



# 排序


```python
# 冒泡排序
# 不管初始列表中的数据如何排列，排一个长度为n的 列表都要进行n-1次遍历；
#总的比较次数是从1到n-1的所有 正整数的和，即1/2(n2-n)。比较复杂度为O(n2)。

# 遍历次数1，比较次数n-1;
# 遍历次数2，比较次数n-2;
# 遍历次数3，比较次数n-3;
def bubbleSort(alist):
    for passnum in range(len(alist)-1,0,-1):# 取值范围是 len(alist)-1，递减1，1；
        for i in range(passnum):
            if alist[i] > alist[i+1]:
                alist[i],alist[i+1] = alist[i+1],alist[i]
    return alist
test = bubbleSort([10,9,8,5])
print(test)
```

    [5, 8, 9, 10]



```python
# 短路冒泡排序
def shortBubbleSort(alist):
    exchanges = True
    passnum = len(alist) - 1
    
    while passnum > 0 and exchanges:
        exchanges = False
        for i in range(passnum):
            if alist[i] > alist[i+1]:
                exchanges = True
                alist[i],alist[i+1] = alist[i+1],alist[i]
            passnum = passnum - 1
            
alist=[20,30,40,90,50,60,70,80,100,110]
shortBubbleSort(alist)
print(alist)
```

    [20, 30, 40, 50, 60, 70, 80, 90, 100, 110]



```python
# 选择排序
def selectionSort(alist):
    for fillslot in range(len(alist)-1,0,-1):
        positionOfMax = 0
        for location in range(1,fillslot+1):
            if alist[location] > alist[positionOfMax]:
                positionOfMax = location
                
        alist[fillslot],alist[positionOfMax] = alist[positionOfMax],alist[fillslot]
            
alist = [54, 26, 93, 17, 77, 31, 44, 55, 20]
selectionSort(alist)
print(alist)

```

    [17, 20, 26, 31, 44, 54, 55, 77, 93]



```python
# 插入排序的算法复杂度仍然是O(n2)
def insertionSort(alist):
    for index in range(1,len(alist)):
        currentvalue = alist[index]
        position = index
        
        while position > 0 and alist[postiopn-1] > currentvalue:
            alist[position] = alist[position-1] # 
            position = position - 1
            
            alist[position] = currentvalue
            
alist = [54, 26, 93, 17, 77, 31, 44, 55, 20]
```


```python
# 希尔排序

```


```python
# 归并排序，归并排序是一种O(nlogn) 的算法
def mergeSort(alist):
    print("Splitting " ,alist)
    if len(alist) > 1:
        mid = len(alist) // 2
        lefthalf = alist[:mid]
        righthalf = alist[mid:]
        
        mergeSort(lefthalf)
        mergeSort(righthalf)
        
        i = 0
        j = 0
        k = 0
        while i < len(lefthalf) and j < len(righthalf):
            if lefthalf[i] <= righthalf[j]:
                alist[k] = lefthalf[i]
                i = i + 1
            else:
                alist[k] = righthalf[j]
                j = j + 1
            k = k + 1
            
        while i < len(lefthalf):
            alist[k] = lefthalf[i]
            i = i + 1
            k  = k + 1
            
        while j < len(righthalf):
            alist[k] = righthalf[j]
            j = j + 1
            k = k + 1
    print("Merging ",alist)
    
alist = [54, 26, 93, 17, 77, 31, 44, 55, 20]
mergeSort(alist)

```

    Splitting  [54, 26, 93, 17, 77, 31, 44, 55, 20]
    Splitting  [54, 26, 93, 17]
    Splitting  [54, 26]
    Splitting  [54]
    Merging  [54]
    Splitting  [26]
    Merging  [26]
    Merging  [26, 54]
    Splitting  [93, 17]
    Splitting  [93]
    Merging  [93]
    Splitting  [17]
    Merging  [17]
    Merging  [17, 93]
    Merging  [17, 26, 54, 93]
    Splitting  [77, 31, 44, 55, 20]
    Splitting  [77, 31]
    Splitting  [77]
    Merging  [77]
    Splitting  [31]
    Merging  [31]
    Merging  [31, 77]
    Splitting  [44, 55, 20]
    Splitting  [44]
    Merging  [44]
    Splitting  [55, 20]
    Splitting  [55]
    Merging  [55]
    Splitting  [20]
    Merging  [20]
    Merging  [20, 55]
    Merging  [20, 44, 55]
    Merging  [20, 31, 44, 55, 77]
    Merging  [17, 20, 26, 31, 44, 54, 55, 77, 93]



```python
# 快速排序

```

# 树


```python
# 树
myTree = ['a',
        ['b',#left subtree
        ['d',[],[]],
        ['e',[],[]]],
        ['c',#right subtree
        ['f',[],[]],
          []]
]
```


```python
print(myTree)
```

    ['a', ['b', ['d', [], []], ['e', [], []]], ['c', ['f', [], []], []]]



```python
myTree[0]
```




    'a'




```python
myTree[1]
```




    ['b', ['d', [], []], ['e', [], []]]




```python
myTree[2]
```




    ['c', ['f', [], []], []]




```python
class BinaryTree:
    def __init__(self,rootObj):
        self.key = rootObj
        self.leftChild = None
        self.rightChild = None

    def insertLeft(self,newNode): # 插入左子树
        if self.leftChild == None: # 当没有左子节点时，简单地将新节点添加到树中即可;
            self.leftChild = BinaryTree(newNode) # 创建新的二叉树对象，设置根的Left属性指向这个对象；
        else:# 当前存在左子节点，我们插入一个节点并将已存在的子节点降级;
            t = BinaryTree(newNode)
            t.leftChild = self.leftChild
            self.leftChild = t
            
    def insertRight(self,newNode):
        if self.rightChild == None:
            self.rightChild = BinaryTree(newNode)
        else:
            t = BinaryTree(newNode)
            t.rightChild = self.rightChild
            self.rightchild = t
            
    def getRightChild(self):
        return self.rightChild
    def getLeftChild(self):
        return self.leftChild
    def setRootVal(self,obj):
        self.key = obj
    def getRootVal(self):
        return self.key

    
r = BinaryTree('a')

```


```python
r.getRootVal()

```




    'a'




```python
print(r.getLeftChild())
```

    None



```python
print(r.getRootVal())
```

    a



```python
r.insertLeft('b')
print(r.getLeftChild())
print(r.getLeftChild().getRootVal())
```

    <__main__.BinaryTree object at 0x00000283E67450F0>
    b



```python
r.insertRight('c')
print(r.getRightChild())
print(r.getRightChild().getRootVal())
```

    <__main__.BinaryTree object at 0x00000283E6706780>
    c



```python
r.getRightChild().setRootVal('hello')
print(r.getRightChild().getRootVal())
```

    hello



```python
class Stack(object):
     # 初始化栈为空列表
    def __init__(self):
        self.items = []
    def is_empty(self):  # 判断栈是否为空，返回布尔值
        return self.items == []
      
    def peek(self): # 返回栈顶元素
        return self.items[len(self.items) - 1] 
    
    def size(self): # 返回栈的大小 
        return len(self.items) 
    
    def push(self, item): # 把新的元素堆进栈里面（压栈，入栈，进栈……） 
        self.items.append(item) 
        
    def pop(self): # 把栈顶元素丢出去（出栈……） 
        return self.items.pop()
    
    def __repr__(self): 
        try:
            return self.items.__repr__()
        except:
            pass
```
