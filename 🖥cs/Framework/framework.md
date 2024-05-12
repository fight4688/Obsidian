# SpringFramework
作用：简化，整合
![](../../asset🧰/Pasted%20image%2020240323112553.png)
![](../../asset🧰/Pasted%20image%2020240423204938.png)
## 基础概念
IoC：由container提供对象，不再由自己管理，将手工生产的产品信息放入工厂机器中
Ioc实现：XML解析+工厂模式+反射机制

三步：![](../../asset🧰/Pasted%20image%2020240422090845.png)
DI：container绑定==DAO和service==，通过DI实现Ioc，将==细节变为抽象==
`关键操作在pom.xml中，是工件配置单`
需要面向==接口和抽象==，而不只是面向对象或接口，==不使用实现类==
container管理的对象称为bean,容器相当于通过变量替代常量

==反射让对象也可以成为变量==，new是创建常量，反射是变量
## 设计原则
1. 开闭原则：可拓展，不可修改


## 操作
通过容器创建对象
![](../../asset🧰/Pasted%20image%2020240423234055.png)
日志使用 
![](../../asset🧰/Pasted%20image%2020240424001844.png)
set注入（name是==方法名==去掉set改为小写）
![](../../asset🧰/Pasted%20image%2020240424094803.png)
构造注入



# SpringMVC

# Maven高级

# SpringBoot


# MyBatisPlus