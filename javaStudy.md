## 继承

[](https://raw.githubusercontent.com/Kathybren/img/master/images/jic.png)
[](https://raw.githubusercontent.com/Kathybren/img/master/images/jc2.png)
[](https://raw.githubusercontent.com/Kathybren/img/master/images/jc3.png)
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