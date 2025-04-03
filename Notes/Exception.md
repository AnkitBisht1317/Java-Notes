# EXCEPTION HANDLING 
- An unaccepted, unwanted event that distrub normal flow of program is called exception.
- Exception handling does not maen repair a exception we have to provide alternative way to contiune rest of program normally this concept of exception handling.
- Inside a method, if an exception occurs, the method where the exception arises is responsible for creating an exception object. This object includes the following information:
  - Name of exception
  - Description of exception
  - Location of exception occurs
- After create exception object method gives the object to the JVM, JVM will check whether method contain any exception handling code or not.
- If method does not contain method handling code then JVM terminate method abnormal and remove corresponding entire of stack this is until main method.
- Throwable class access root for java exception hierarchy
- Throwable class define 2 child class
   - Exception
   - Error

   ## Error
     - Most of the error are not caused by our program and these are due to lack of system resource error are not recoverable.
       
   ## Exception
     - Most of the time exception are caused by our program and these are recoverable.
     - There are two type of exception

   ### Checked Exception
     - The exception which are checked by complier for normal flow of program are called checked exception.
     - In our program there is a chance of raise checked exception then we sholud handle exception by try catch or throws keyword otherwise we will get complie time error.

   ### Unchecked Exception
     - The exception which are not checked by complier whether programmer handling or not such type of exception are called unchaecked exception.
 
## How to Handle Exception 
- there are various method to handle exception is java
  
### 1. try Block 
- Contains code that might throw an exception.
- If an exception occurs, the rest of the try block is skipped, and control moves to the catch block.

### 2. Catch Block
- Executes only if an exception occurs in the try block.
- Catches and handles the exception.
- Can specify the type of exception to catch (e.g., ArithmeticException, NullPointerException).

```java
public class TryCatchExample {
    public static void main(String[] args) {
        try {
            int a = 10;
            int b = 0;
            int result = a / b;
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Error: Division by zero is not allowed!");
            System.out.println("Exception details: " + e.getMessage());
        }
    }
}
```
### 3. Finally Block
- Finally is a block always associated with try and catch to maintain clean up code.
- The benefit of finally block is, if we will be excuted whthere exception rise or not and exception handle or not handle.
``` java
  public class TryCatchExample {
    public static void main(String[] args) {
      try {
    let result = 10 / 0;
    if (!isFinite(result)) {
        throw new Error("Division by zero!");
    }
    console.log("Result:", result);
   } catch (error) {
    console.error("Error:", error.message);
  } finally {
    console.log("Execution completed.");
  }
  }
  }
```
### 4. Throw 
- Sometime we can create exception object explicitly we can handover JVM manually for this we use throw keyword.
- Hence the main objective of throw keyword is to handover our created exception to the JVM.
- Best use of throw keyword is for user define exception or customized exception .
- After throw statement we not write any statement directly otherwise we will get complie time error saying unreachable statement.
``` java
// Custom exception class
class InvalidAgeException extends Exception {
    // Default constructor
    public InvalidAgeException() {
        super("Age must be between 18 and 60!");
    }

    // Parameterized constructor (custom error message)
    public InvalidAgeException(String message) {
        super(message);
    }
}
public class CustomExceptionExample {
    public static void validateAge(int age) throws InvalidAgeException {
        if (age < 18 || age > 60) {
            throw new InvalidAgeException("Age " + age + " is invalid!");
        } else {
            System.out.println("Age is valid.");
        }
    }

    public static void main(String[] args) {
        try {
            validateAge(15); // This will throw InvalidAgeException
        } catch (InvalidAgeException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```
### Throws 
- In our program if there is a possibility of raisin checked exception then compulsory we should handle checked exception othrewise we will get complie time error.
- we handle checked exception two way try catch block or throws keyword.
- we use throws keyword methos or construtor but not for class.
```java
import java.io.*;

class SimpleThrowsExample {
    
    // This method declares that it "throws" IOException
    public static void readFirstLine(String filePath) throws IOException {
        BufferedReader reader = new BufferedReader(new FileReader(filePath));
        System.out.println("First line: " + reader.readLine());
        reader.close();
    }

    public static void main(String[] args) {
        try {
            readFirstLine("test.txt"); // Call the risky method
        } catch (IOException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```
