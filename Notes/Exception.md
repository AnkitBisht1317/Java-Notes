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

   ### Exception
     - Most of the time exception are caused by our program and these are recoverable.

   ### Error
     - Most of the error are not caused by our program and these are due to lack of system resource error are not recoverable.
