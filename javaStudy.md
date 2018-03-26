## 继承

![](https://raw.githubusercontent.com/Kathybren/img/master/images/jic.png)
![](https://raw.githubusercontent.com/Kathybren/img/master/images/jc2.png)
![](https://raw.githubusercontent.com/Kathybren/img/master/images/jc3.png)
```
class Teacher {
    private String name;
    private String school;
    
    public Teacher(String name, String school) {
        this.name = name;
        this.school = school;
    }
    public void teaching () {
        System.out.println("授课")
    }
}
```
```
class javaTeacher extends Teacher {
    public javaTeacher (String name, String school) {
        super(name, school);
    }
    public void teaching(){
        super.teaching();
        System.out.prinln("教学");
    }
}
```
## final 关键字

![](https://raw.githubusercontent.com/Kathybren/img/master/images/ffcz.png)
![](https://raw.githubusercontent.com/Kathybren/img/master/images/final.png)
```
class demo {
    public final int number = 1 // 常量
    public void showNumber() {
        // number++ // 常量不能被修改
        System.out.println(number)
    }
}
```
```
class demo1 extends demo{
    // 如果demo方法有final修饰，则子类不能方法重写
    // 类也不能继承
    public void showNumber1() {
        System.out.println("number")
    }
}
```
## 抽象类
![](https://raw.githubusercontent.com/Kathybren/img/master/images/cxl.png)
![](https://raw.githubusercontent.com/Kathybren/img/master/images/cxl1.png)
![](https://raw.githubusercontent.com/Kathybren/img/master/images/cxl2.png)
```
class Employee {
    private int number;
    private String name;
    private double salary;
    public Employee (int number, String name, Double salary) {
        this.number=number;
        this.name =name;
        this.salary = salary;
    }
    // 抽象方法声明
    public abstrace void work()
}
```
//一旦一个类继承了抽象类，那么这个类要么实现抽象类中抽象方法，要么继续抽象
```
class JavaTeacher extends Employee {
    public JavaTeacher(int number, String name, Double salary) {
        super(number,  name,  salary)
    }
    public void work () {
        System.out.println("java")
    }
}
```
```
class Leader extends Employee {
    private double allowance;//津贴
    public Leader(int number, String name, Double salary，double allowance) {
        super(number,  name,  salary)
        this.allowance=allowance
    }
    public void work () {
        System.out.println("leader")
    }
}
```
# 模板模式
```
abstract class Teacher {
    public void prepared() {
        System.out.println("准备")
    }
    public void end() {
        System.out.println("结束")
    }
    public abstract void teaching()
    public void work() {
        // 1准备
        prepared()
        // 2进行授课
        teaching()
        // 3结束
        end()
    }
}
```
```
class DBteacher extends Teacher{
    public void teaching() {
        System.out.println("打开数据库")
        System.out.println("优化")
    }
}
```
// 调用
```
Teacher t1 = new DBteacher();
t1.work()
```
// 接口
![](https://raw.githubusercontent.com/Kathybren/img/master/images/jk.png)
![](https://raw.githubusercontent.com/Kathybren/img/master/images/jk1.png)
```
interface Iability{
    // 接口中只能放公有的静态常量和抽象方法
    public static final int number = 1
    // 可省略
    int number =1
    public abstract void show();
}
```
```
class Child{
    public void eat() {
        System.out.println("吃米饭")
    }
}
class Dog{
    public void eat() {
        System.out.println("吃骨头")
    }
}
class Person {
    public void feed(Child child) {
        child.eat()
    }
    public void feed(Dog dog) {
        dog.eat()
    }
}
```
//调用
```
Person p= new Person();
Child c= new Child();
Dog d= new Dog();
p.feed(c);
p.feed(d);
```

//接口实现
```
interface Iability{
void eat()
}
class Child implements Iability{
    public void eat() {
        System.out.println("吃米饭")
    }
}
class Dog implements Iability{
    public void eat() {
        System.out.println("吃骨头")
    }
}
```
//接口的引用变量可以引用实现类的对象
```
class Person {
    public void feed(Iability iability) {
        iability.eat()//动态绑定
    }
}
```