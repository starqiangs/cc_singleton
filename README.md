# c_singleton
c++ singleton mode

### backlog
针对单例模式进行展示

### 思想
一个类不管创建多少次对象，永远得到该类型一个对象的实例

饿汉模式：还没创建对象，对象就已经产生了
懒汉模式：唯一的实例对象，知道第一次获取的时候才产生


饿汉模式：（线程安全的）
task：
```
1.构造函数私有化 
2.拷贝构造+赋值运算符重载 = delete
3.定义一个唯一的类的实例对象
4.获取类唯一对象的接口
```

### 注意：
- 在C++中，类的静态成员（static member）必须在类内声明，在类外初始化，像下面这样。 为什么？ 因为静态成员属于整个类，而不属于某个对象，如果在类内初始化，会导致每个对象都包含该静态成员，这是矛盾的。
- 懒汉模式获取对象调用的时候，是抢占式获取对象实例接口，要是不同的线程同时判断出当前的对象不存在，要去创建唯一的对象实例，就造成了多个对象同时存在，单例也就不是单例了

### 例子
- 框架类 
- 日志类
- 数据库模块