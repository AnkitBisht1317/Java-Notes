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
- Two thread can communicate with each other by using wait(), notify() and notifyAll() method.
- The wait() method is used in multithreading when a thread wants to pause its execution and release the lock of the object it holds.
- The thread that is waiting for some condition (like resource availability or update) should call wait(), releasing the lock and entering the waiting state.
- The thread that performs the update is responsible for calling notify(). This notifies the waiting thread, which then resumes execution and uses the updated data.

<img width="2471" height="1151" alt="Image" src="https://github.com/user-attachments/assets/703c8771-69dc-44b0-b90c-418355ffb400" />

#### Notify vs NotifyAll
- "We can use the notify() method to give notification to only one waiting thread. If multiple threads are waiting, only one of them will be notified, and the remaining threads will continue waiting until further notifications are received.
- Which thread will be notified, we cannot predict — it depends on the JVM.
- We can use notifyAll() to send a notification to all waiting threads of a particular object. Even though multiple threads are notified, they execute one by one because each thread requires the object's lock, and only one thread can hold the lock at a time.

## DeadLock 
- If two thread waiting for each other forever such type of infinite waiting is called deadlock.
- Synchronized keyword is only reason for deadlock situation heance while using synchronized keyword we have to take special case.
- There are no resoution techanique for deadlock but some prevention technique are avaiable.

#### DeadLock vs Stravation
- Long waiting of a thread where waiting never ends is called deadlock.
- whereas long waiting of a thread where waiting end certain point is called stravation.
