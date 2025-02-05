# DATA HIDDING  : 
- Outside person can not access our internal data directly or our internal data should not go out directly this OOPS feature is nothing but data hidding.
- After validation outside person can access our internal data.
    - Eaxmple - After providing proper user name or password we can able to access our gamil inbox information.
- By declaring data member (variable) as private we can achive data hidding.
  ```java
   class Student {
    private int age;  // Data Hiding: Age is private
    // Setter method to set age
    public void setAge(int age) {
        if (age > 0) { // Adding a simple validation
            this.age = age;
        } else {
            System.out.println("Age cannot be negative or zero!");
        }
    }
    // Getter method to get age
    public int getAge() {
        return age;
    }
  }
   public class Main {
    public static void main(String[] args) {
        Student student = new Student();
        student.setAge(20);  // Setting age using setter method
        System.out.println("Student's Age: " + student.getAge()); // Accessing age using getter method
    }
  }
  ``` 
- The main advantage of data hidding is security.
- It is highly recommand to use declare data member as private.
