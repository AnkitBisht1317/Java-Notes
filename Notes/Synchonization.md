# Synchronization 
- Synchronization is modifer applicable only method or block but not for variable and class.
- If multiple thread try to operate at a same time, to same java object then there may be chance of data inconsistency problem, to overcome this problem we should go for synchronized keyword.
- If a method or block decalre as synchorized then at a time only one thread alllow to execute that method or block on the given object so data inconsistency problem is resolve.
- The main disadvantage of synchronized keyword is it increase waiting time of thread and create performance probelm, if there is no specific requirement then not use synchronized keyword.
- Internally, the concept of synchronization in Java is implemented using locks. Every object in Java has a unique intrinsic lock (also called a monitor). This lock mechanism only comes into action when we use the synchronized keyword. Without synchronized, the lock is not used.
- If a thread wants to execute a synchronized method on a given object, it must first acquire the lock of that object.Once the thread acquires the lock, it is allowed to execute any synchronized method of that object.After the method completes execution, the thread automatically releases the lock.
- acquire and release lock internally take care by JVM. programmer not responsible that lock.
- While a thread execute synchronized method on a given object the remaing not allow to execute any synchronized method at a time on the same object but reamaining thread allow to execute non-synchorinzed method at a time.

![Image](https://github.com/user-attachments/assets/51d454f9-6db0-4958-ba7f-56c84cfce191)

## Syenchronized Block 
- If very few code required synchronition then it is not recommand to decalre entire method to synchroized, we have to enclosed those few line of code by using synchronized block.
- The main advantage of synchroized block over synchronized method is it reduced waiting time of thread and impore performance of system.

## InterThread Communication
- 
