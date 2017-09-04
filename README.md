# java基础内容
## java 语言的特点
- 一种面向对象的语言
- 一种平台无关的语言
- 一种健壮的语言，吸收了从C/C++语言的优点，但是去掉了影响其程序健壮性的部分（如指针、内存的申请和释放等）
- java源文件以 "java"  为扩展名。源文件基本组成部分是类。
- 一个源文件最多只能有一个 public类，其他类的个数不限，如果源文件只包含一个 public 类，它必须按该类名进行命名。
## java基础语法
### 标识符命名规则：
1. 由字母、下划线 "_"、美元符号 "$"或数字组成。
2. 以字母、下划线或美元符号开头。
3. 大小写敏感，长度无限制。
4. 不能与 java关键字重名。
### java变量的分类
- 按被声明的位置划分：
1. 局部变量：方法或语句块内部定义的变量。
2. 成员变量：方法外部、类的内部定义的变量。
  注意：类的外部不能有变量的声明。
- 按所属数据类型分类：
1. 基本数据类型变量：数值型、字符型、布尔型。
2. 引用数据类型变量：类、数组、接口
- 成员变量和局部变量的区别：
1. 在类中的位置不同：成员变量：在类中方法外。局部变量：在方法定义中或者方法声明上
2. 在内存中的位置不同：成员变量：在堆内存中。 局部变量：在栈内存中。
3. 生命周期不同：成员变量：随着对象的创建而存在，随着对象的消失而消失。局部变量：随着方法的调用而存在，随着方法的调用完毕而消失。
4. 初始化值不同：成员变量：有默认值初始化。局部变量：没有默认值初始化。
### java 基本数据类型 (4类8种基本数据类型)
- 逻辑型——boolean
- 文本型——char
- 整数型——byte short int long 
- 浮点数型——float double
### 基本数据类型转化
- boolean类型不可转换成其他数据类型
- 整型、字符型、浮点型的数据类型的转化遵循以下规则:容量小的类型自动转为容量大的数据类型  byte,short,char>int>long>float>double
### 自增和自减运算符
- 注：（++）--    *在前时先运算再取值   *在后时先取值再运算
- 例子：
```
int i1=10, int i2=20  int i=(i2++) sout(i,i2)---->i=20,i2=21  
i=(++i2) sout(i,i2)----->i=22,i2=22
```
### 字符串运算符
- "+"运算符两侧的操作数中只要有一个是字符串类型，系统会自动将另一个数字转化为字符串类型然后再进行链接。
### For 循环语句
- for 语句有如下形式：for（表达式1；表达式2；表达式3）{语句;...;}
- 执行过程：
* 首先执行表达式1，接着执行表达式2，若表达式2的值为 true,则执行语句。接着计算表达式3，再判断表达式2的值，依次重复下去。直到表达式2的语句
为 FALSE。for 语句中三个表达式的值可以省略。
### while & do while语句
- while语句形式：
1. while（逻辑表达式）{语句；... ;}  执行过程：先判断表达式的值，若为 true,则执行后面的语句。然后再次判断条件反复执行，直到条件不成立为止。
2. do{语句；... ;}  while(逻辑表达式)； 执行过程： 先执行语句，再判断逻辑表达式的值，若为 true,再执行语句，否则循环结束。
### break & continue语句
- break 语句用于终止某个语句块的执行，用在循环语句体中，可以强行退出循环。
- continue 语句用在循环体中，用于终止某次循环过程，跳过 循环体中continue语句下面未执行的循环语句，开始下一次循环过程。
### java的方法
- 声明格式：【修饰符1 修饰符2 ......】 返回值类型  方法名（形式参数列表）{java语句...}
- java中使用下列形式进行调用方法：对象名.方法名
- java中进行函数调用中传递参数时，遵循值传递的原则：基本类型传递的是该数据值本身，引用类型传递的是对对象的引用，而不是对象本身。
## java 面向对象
### 对象和类的定义
- 对象：是该类的一个具体实例
- 类：是描述同一类事物共同特征的一个抽象
### 面向对象思想
1. 有哪些类，有哪些对象。
2. 再考虑这些类和这些对象，每一种类和每一种对象都应该有什么属性和方法。
3. 再考虑类和类之间具备了什么关系。
### 构造方法（构造函数）
- 使用 new+构造方法创建一个新的对象
- 构造函数是定义在 java 类中的一个用来初始化对象的函数
- 构造函数与类同名且没有返回值。
### 方法的重载
- 定义：一个类中可以定义有相同的名字，但参数（参数个数、参数类型）不同的多个方法。
### this 关键字
- 在类的方法定义中使用 this 关键字代表使用该方法的对象的引用。
- 当必须指出当前使用方法的对象是谁时要使用 this 关键字。
- 有时使用 this 可以处理成员变量和参数重名的情况。
- this 可以看做一个变量，它的值是当前对象的引用。
### static关键字
- 在类中，用 static 申明的成员变量是静态成员变量，它为该类的公用变量。第一次使用时就被初始化，对于该类的所有变量来说，static 成员变量只有一份。
- static申明的方法为静态方法，在调用该方法时，不会将对象的引用传递给它，所以在 static 中不能访问非 static 成员。
- 静态方法不再针对某个对象来调用用，所以不能访问非静态成员。
- 可以通过对象引用或类名（不需要实例化）来访问静态成员。
### 静态代码块
- 静态代码块：随着类的加载而执行。而且只执行一次。
- 作用:用于给类进行初始化。
### 访问控制
- JAVA 权限修饰符置于类的成员定义前，用来限定其他对象对该类成员对象的访问权限。
```
类内部：private、public、protected、default
同一个包：public、protected、default
子类：protected、public
任何地方：public
对于 class权限修饰，只可以用 public 和 default
default 类只能被同一个包内部的类访问。
```
### 类的继承
- java中通过关键字 extends实现继承。
- 通过继承子类拥有了基类的所有成员（成员变量很方法）
- JAVA 只支持单继承，不允许多继承。一个子类只能有一个基类，一个基类可以派生出多个子类。
### 方法的重写
- 重写方法和被重写方法必须具有相同方法名称，参数列表和返回类型。
- 重写方法不能使用比被重写方法更严格的访问权限。
### super关键字
- this 当前对象的引用，super 当前对象里面父类对象的引用
### 继承中的构造方法
- 子类构造的过程中必须调用父类的构造方法
- 子类可以在自己的构造方法中使用 super（参数列表）调用父类的构造函数。使用 this 调用本类（参数列表）另外的构造函数。
- 如果调用 super 必须写在子类构造方法的第一行。
- 如果子类的构造方法没有显示调用父类的构造方法，则系统默认调用父类（基类）无参数的构造方法。
- 如果子类的构造方法中既没有显示调用父类的构造方法，而父类中又没有无参的构造方法，则编译出错。
### equals方法
- Object 类中public boolean equals(Object obj)----提供定义对象是否相等的逻辑
- Object的 equals方法定义为 x.equals(y),当 x和 y 是同一个对象时返回为 TRUE 否则返回为 false
- 如 String、Date等类，重写了 Object 中的 equals 方法。调用这些类的 equals方法， x.equals(y)，当 x与 y所引用的对象是同一类对象且属性内容相等时（并不一定是相同对象），返回 TRUE 否则返回 FALSE。
- ==与 equals的区别：String s1=new String("apple"); String s2=new String("apple"); s1==s2——>false; s1.equals(s2)——>true;  
- ==比较的是两个对象的地址；equals比较的是两个对象的内容。
- 如果一个类没有自己定义 equals方法，那么它将继承 Object 类中的 equals 方法。
### 对象的转型
- 一个基类的引用类型变量可以指向其子类的对象
- 一个基类的引用不可以访问其子类对象新增加的成员（属性与方法）
- 可以使用引用变量类型 intanceof类名来判断该引用型变量所"指向"的对象是否属于该类或该类的子类。
- 子类的对象可以当做基类的对象来使用称作向上转型，反之称作向下转型。
### 动态绑定
- 是指在执行期间而非编译期间，判断所引用对象的实际类型，根据其实际类型来调用其相应的方法。（增加了程序的可扩展性）
### 多态
1. 要有继承
2. 要有重写
3. 父类对象指向子类引用。
### 抽象类
- 使用 abstract 这个关键字来修饰。
- 含有抽象方法的类必须申明为抽象类，抽象类必须被继承，抽象方法必须被重写。
- 抽象类不能被实例化
- 抽象方法只需申明，不需要实现
### final 关键字
- final 变量的值不能被改变（final 的成员变量、final 的局部变量）
- final 的方法不能被重写
- final 的类不能够被继承。
### 接口
- 定义：是抽象方法和常量值定义的集合。
- 从本质上讲，接口是一种特殊的抽象类，这种抽象类中只包含常量和方法的定义，而没有变量和方法的实现。
- 多个无关的类可以实现同一接口
### 接口的特性
- 接口可以多重实现
- 接口中申明的属性默认为 public static final 的；也只能是它；
- 接口中只能定义抽象方法，而且这些方法默认是public 的，也只能是 public 的，
- 接口可以继承其他接口，并添加新的属性和抽象方法。
- 一个类可以实现多个无关的接口
- 与继承关系相似，接口与实现类之间存在多态性
### 抽象类和接口的异同点:
- 相同点: 都是不断向上抽取而来的。
- 不同点: 
1. 抽象类需要被继承，而且只能单继承。接口需要被实现，而且可以多实现。  
2. 抽象类中可以定义抽象方法和非抽象方法，子类继承后，可以直接使用非抽象方法。接口中只能定义抽象方法，必须由子类去实现。
3. 抽象类的继承，是is a关系，在定义该体系的基本共性内容。接口的实现是 like a 关系，在定义体系额外功能。
### 异常
- 在运行时期发生的不正常情况。
- throws和 throw 的区别：
1. throws使用在函数上，throw 使用在函数内。
2. throws 抛出的是异常类，可以抛出多个，用逗号隔开。throw 抛出的是异常对象。
### 异常处理的原则：
1. 函数内容如果抛出需要检测的异常，那么函数上必须要申明。否则必须在函数内用 try{}catch（）捕捉，否则编译失败。
2. 如果调用到了申明异常的函数，要么 trycatch，要么 throws，否则编译失败。
3. 功能内容可以解决，用 catch，不能解决用 throws,throws告诉调用者，由调用者解决。
4. 一个功能如果抛出了多个异常，那么调用时，必须有对应多个 catch 进行针对性处理。
### 异常注意事项
1. 子类在覆盖父类方法时，如果父类方法抛出了异常，那么子类方法必须抛出父类的异常或者该异常的子类。
2. 如果父类抛出多个异常，那么子类只能抛出父类异常的子类。
### 数组总结:
- 数组的定义:数组是相同类型数据的集合，描述的是相同类型的若干个数据按照一定的先后顺序排列组合而成，其中每一个数据称作一个数组元素，每个数组元素可以通过一个下标来访问它们。 
- 数组的四个基本特点:
1. 长度固定，一旦被创建它的长度就是不可改变的;
2. 其元素类型必须是相同类型，不允许出现混合类型;
3. 数组中的元素可以是任何数据类型，包括基本数据类型和引用数据类型;
4. 数组变量属于引用类型，数组也可以看做是对象，数组中的每个元素相当于该对象的成员变量，数组本身就是对象，Java中对象是在堆中的，因此数组无论保存原始类型还是其他对象类型，数组本身是在堆中的。
- 数组的下标合法区间是[0,length-1]。 
- 数组的拷贝:System.arrayCopy(源数组，从哪开始，目标数组，从哪开始贴，粘几个)。 
- 数组排序:Arrays.sort(被排序的数组)。 二分法查找:Arrays.binarySearch(哪个数组，数组中的什么元素)。
- 数组的下标合法区间是[0,length-1]。 
- 数组的下标合法区间是[0,length-1]。
填充:Arrays.fill(a， 2， 4, 100)。//将数组a中2到4的索引的元素替换为100 获取数组的长度:数组.length，如a.length，获取数组a的元素个数;a[0].length，表示获取二维数组中第一个数组的长度。 
- 数组的遍历:可以使用for循环或者for嵌套循环(对于二维数组)，也可以使用增强for循环来对数组进行遍历，增强for循环格式:for(变量类型 变量名:被遍历的数组)
## 常用类 API
### String类的特点:
- 字符串对象一旦被初始化就不会被改变。
### String 类中的方法及使用
1. 获取:
```
获取字符串中字符的个数(长度). int length();
- 根据位置获取字符。
char charAt(int index);
- 根据字符获取在字符串中的第一次出现的位置. int indexOf(int ch)
int indexOf(int ch,int fromIndex):从指定位置进行ch的查找第一次出现位置
int indexOf(String str);
int indexOf(String str,int fromIndex);
- 根据字符串获取在字符串中的第一次出现的位置. int lastIndexOf(int ch)
int lastIndexOf(int ch,int fromIndex):从指定位置进行ch的查找第一次出现位置 
int lastIndexOf(String str);
int lastIndexOf(String str,int fromIndex); 获取字符串中一部分字符串。也叫子串.
String substring(int beginIndex, int endIndex)//包含begin 不包含end 。 String substring(int beginIndex);
```

2. 转换。
```
- 将字符串变成字符串数组(字符串的切割)
 String[] split(String regex):涉及到正则表达式.
- 将字符串变成字符数组。
char[] toCharArray();
- 将字符串变成字节数组。
 byte[] getBytes();
- 将字符串中的字母转成大小写。
String toUpperCase():大写
String toLowerCase():小写
- 将字符串中的内容进行替换
String replace(char oldch,char newch);
String replace(String s1,String s2);
- 将字符串两端的空格去除。
String trim();
- 将字符串进行连接 。
String concat(string); 
3. 判断
- 两个字符串内容是否相同啊?
boolean equals(Object obj);
boolean equalsIgnoreCase(string str);忽略大写比较字符串内容。
-  字符串中是否包含指定字符串?
boolean contains(string str);
-  字符串是否以指定字符串开头。是否以指定字符串结尾。
boolean startsWith(string);
boolean endsWith(string); *
4. 比较。
```
### StringBuffer用法及其使用
- StringBuffer:就是字符串缓冲区。用于存储数据的容器。
- 特点:
1. 长度的可变的。
2. 可以存储不同类型数据。
3. 最终要转成字符串进行使用。 
4. 可以对字符串进行修改。
- 应该具备什么功能呢? 
```
1. 添加:
StringBuffer append(data);
StringBuffer insert(index,data);
2. 删除:
StringBuffer delete(start,end):包含头，不包含尾。
StringBuffer deleteCharAt(int index):删除指定位置的元素
3. 查找:
char charAt(index);
int indexOf(string);
int lastIndexOf(string);
4. 修改:
StringBuffer replace(start,end,string);
void setCharAt(index,char);
```

### StringBuffer 和 StringBuilder 区别
- 不同的是: StringBuffer是线程同步的。通常用于多线程。StringBuilder是线程不同步的。通常用于单线程。 它的出现提高效率 
## 集合框架（容器）
### Set、List、Map大总结
- 集合类的由来: 对象用于封装特有数据，对象多了需要存储，如果对象的个数不确定。 就使用集合容器进行存储。
- 集合特点:
1. 用于存储对象的容器。 2. 集合的长度是可变的。 3. 集合中不可以存储基本数据类型值。
- 集合容器因为内部的数据结构不同，有多种具体容器。不断的向上抽取，就形成了集合框架。
- 框架的顶层Collection接口:
- Collection的常见方法:
```
1. 添加。
boolean add(Object obj):
boolean addAll(Collection coll):
2. 删除。
boolean remove(object obj):
boolean removeAll(Collection coll); void clear();
3. 判断:
boolean contains(object obj):
boolean containsAll(Colllection coll); boolean isEmpty():判断集合中是否有元素。
4. 获取:
int size():
Iterator iterator():取出元素的方式:迭代器。 该对象必须依赖于具体容器，因为每一个容器的数据结构都不同。 所以该迭代器对象是在容器中进行内部实现的。 对于使用容器者而言，具体的实现不重要，只要通过容器获取到该实现的迭代器的对象即可，也就是iterator方法。 Iterator接口就是对所有的Collection容器进行元素取出的公共接口。其实就是抓娃娃游戏机中的夹子!
5. 其他:
boolean retainAll(Collection coll);取交集。
Object[] toArray():将集合转成数组。
```

- List:有序(存入和取出的顺序一致),元素都有索引(角标)，元素可以重复。 
- Set:元素不能重复,无序。
- List:特有的常见方法:有一个共性特点就是都可以操作角标。
```
1. 添加
void add(index,element); void add(index,collection);
2. 删除;
Object remove(index):
3. 修改:
Object set(index,element);
4. 获取:
Object get(index);
int indexOf(object);
int lastIndexOf(object); List subList(from,to);
```

- list集合是可以完成对元素的增删改查。
- List: 
1. Vector:内部是数组数据结构，是同步的。增删，查询都很慢!
2.ArrayList:内部是数组数据结构，是不同步的。替代了Vector。查询的速度快。 
- LinkedList:内部是链表数据结构，是不同步的。增删元素的速度很快。
- List: 1. Vector:内部是数组数据结构，是同步的。增删，查询都很慢!
3. LinkedList:
- List: 
```
1. Vector:内部是数组数据结构，是同步的。增删，查询都很慢!
   addFirst();
   addLast():
   offerFirst();
   offetLast();
   getFirst();.//获取但不移除，如果链表为空，抛出NoSuchElementException. getLast();
   peekFirst();//获取但不移除，如果链表为空，返回null.
   peekLast():
   removeFirst();//获取并移除，如果链表为空，抛出NoSuchElementException. removeLast();
   pollFirst();//获取并移除，如果链表为空，返回null.
   pollLast();
 ```
- Set:元素不可以重复，是无序。 Set接口中的方法和Collection一致。
- HashSet: 内部数据结构是哈希表 ，是不同步的。
- 如何保证该集合的元素唯一性呢? 
```
是通过对象的hashCode和equals方法来完成对象唯一性的。 如果对象的hashCode值不同，那么不用判断equals方法，就直接存储到哈希表中。 如果对象的hashCode值相同，那么要再次判断对象的equals方法是否为true。 如果为true，视为相同元素，不存。如果为false，那么视为不同元素，就进行存储。
记住:如果元素要存储到HashSet集合中，必须覆盖hashCode方法和equals方法。 一般情况下，如果定义的类会产生很多对象，比如人，学生，书，通常都需要覆盖equals，hashCode 方法。
```
- 建立对象判断是否相同的依据。
```
- TreeSet:可以对Set集合中的元素进行排序。是不同步的。 判断元素唯一性的方式:就是根据比较方法的返回结果是否是0，是0，就是相同元素，不存。
TreeSet对元素进行排序的方式一: 让元素自身具备比较功能，元就需要实现Comparable接口。覆盖compareTo方法。
如果不要按照对象中具备的自然顺序进行排序。如果对象中不具备自然顺序。
可以使用TreeSet集合第二种排序方式二:
让集合自身具备比较功能，定义一个类实现Comparator接口，覆盖compare方法。 将该类对象作为参数传递给TreeSet集合的构造函数。
if(this.hashCode()== obj.hashCode() && this.equals(obj))
```
- 哈希表确定元素是否相同 
1. 判断的是两个元素的哈希值是否相同。如果相同，在判断两个对象的内容是否相同。
2. 判断哈希值相同，其实判断的是对象的hashCode的方法。判断内容相同，用的是equals方法。
- 注意:如果哈希值不同，是不需要判断equals。
### Map的使用
- Map:一次添加一对元素。Collection 一次添加一个元素。 Map也称为双列集合，Collection集合称为单列集合。 其实map集合中存储的就是键值对。 map集合中必须保证键的唯一性。
- 常用方法: 
```
1. 添加。
value put(key,value):返回前一个和key关联的值，如果没有返回null. 
2. 删除。
void clear():清空map集合。
value remove(key):根据指定的key翻出这个键值对。
3. 判断。
boolean containsKey(key): 
boolean containsValue(value):
boolean isEmpty();
4. 获取。
value get(key):通过键获取值，如果没有该键返回null。
当然可以通过返回null，来判断是否包含指定键。 int size(): 获取键值对的个数。
```
- Map常用的子类:
1. Hashtable :内部结构是哈希表，是同步的。不允许null作为键，null作为值。
2. Properties:用来存储键值对型的配置文件的信息，可以和IO技术相结合。
- HashMap : 内部结构是哈希表，不是同步的。允许null作为键，null作为值。 
- TreeMap : 内部结构是二叉树，不是同步的。可以对Map集合中的键进行排序。
### 其他类 API 使用
- Math:提供了操作数学运算的方法，都是静态的。
- 常用的方法:
- ceil():返回大于参数的最小整数。
- floor():返回小于参数的最大整数。
- round():返回四舍五入的整数。
- pow(a,b):a的b次方。
### IO 流
```
字符流:
FileReader；
FileWriter；
BufferedReader；
BufferedWriter；
字节流:
InputStream； OutputStream。
操作文件的字节流对象。
FileOutputStream；
FileInputStream；
BufferedOutputStream；
BufferedInputStream；
字符流和字节流之间的转换动作。
```

- 转换流:
```
InputStreamReader isr = new InputStreamReader(new FileInputStream("a.txt"));
InputStreamReader isr = new InputStreamReader(new FileInputStream("a.txt"),"gbk"); 
FileReader fr = new FileReader("a.txt");
FileWriter fw = new FileWriter("b.txt");
OutputStreamWriter osw = new OutputStreamWriter(new FileOutputStream("b.txt")); 
OutputStreamWriter osw = new OutputStreamWriter(new FileOutputStream("b.txt"),"gbk");
```

### File类:
- 用于将文件和文件夹封装成对象。
```
1. 创建。
boolean createNewFile():如果该文件不存在，会创建，如果已存在，则不创建。不会像输出流一样会覆盖。
boolean mkdir();
boolean mkdirs();
2. 删除。
boolean delete(); void deleteOnExit();
3. 获取:
String getAbsolutePath(); 
String getPath();
String getParent();
String getName();
long length();
long lastModified();
4. 判断:
boolean exists(); 
boolean isFile(); 
boolean isDirectory();
```
- IO中的其他功能流对象:
1. 打印流: PrintStream:字节打印流。
- 特点:
1. 构造函数接收File对象，字符串路径，字节输出流。意味着打印目的可以有很多。 
2. 该对象具备特有的方法 打印方法 print println,可以打印任何类型的数据。 
3. 特有的print方法可以保持任意类型数据表现形式的原样性，将数据输出到目的地。
- 对于OutputStream父类中的write，是将数据的最低字节写出去。
- PrintWriter:字符打印流。
- 特点:
1. 当操作的数据是字符时，可以选择PrintWriter，比PrintStream要方便。 
2. 它的构造函数可以接收 File对象，字符串路径，字节输出流，字符输出流。
3. 构造函数中，如果参数是输出流，那么可以通过指定另一个参数true完成自动刷新，该true对println方法有效。



