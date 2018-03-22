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