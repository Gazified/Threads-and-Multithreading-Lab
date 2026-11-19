# Threads and Multithreading Laboratory

## Student Information
- Name: Gazawe G. Casim
- Section: B186.1
- Date: 11/19/2026

## Laboratory Description
This laboratory demonstrates thread creation,
multithreading, thread coordination, and
shared-resource management using Python.

## Completed Tasks
1. Single Thread
2. Multiple Threads
3. Thread Synchronization using join()
4. Shared Resource Management using Lock()

## Learning Outcomes
- Create and execute threads.
- Demonstrate concurrent execution.
- Explain thread coordination.
- Apply locks to protect shared resources.

---


---

## Task 1 – Creating and Executing a Single Thread

### Screenshot
<img width="1092" height="784" alt="task1" src="https://github.com/user-attachments/assets/0d22276c-98a4-47f8-9969-abbdc128e5ab" />


### Task 1 Questions

**Task 1 – Question 1: What is the purpose of threading.Thread()?**

The purpose of threading.Thread() is to create a new thread object that runs a specified function, which is set through the target argument.

**Task 1 – Question 2: What happens when start() is executed?**

When start() is executed, the thread begins running its target function separately from the main program.

**Task 1 – Question 3: What is the purpose of join()?**

The purpose of join() is to make the main program wait until the thread finishes its execution.

**Task 1 – Question 4: What happens if join() is removed?**

If join() is removed, the main program no longer waits for the thread, so "Program completed." may be printed before the thread finishes.

---

## Task 2 – Implementing Multiple Threads

### Screenshot
<img width="1081" height="781" alt="task2" src="https://github.com/user-attachments/assets/4ea93b71-a619-4c5f-aeff-14311cf469e9" />


### Task 2 Questions

**Task 2 – Question 1: How many threads are created in the program?**

Two threads are created in the program, t1 and t2, not counting the main thread.

**Task 2 – Question 2: Do the two threads execute independently?**

Yes. Each thread runs its own function independently of the other.

**Task 2 – Question 3: Why might the output order change when the program is executed again?**

The output order may change because the operating system scheduler decides when each thread gets CPU time, and this timing is different in every run.

**Task 2 – Question 4: What is the difference between sequential and concurrent execution?**

Sequential execution completes one task entirely before the next one starts. Concurrent execution allows multiple tasks to overlap and make progress during the same period.

---

## Task 3 – Thread Synchronization Using join()

### Screenshots

**With join()**

<img width="1107" height="774" alt="task3-with-join" src="https://github.com/user-attachments/assets/ce3190d4-fe31-46f6-93bc-c0f3c5c37e92" />


**Without join()**

<img width="1105" height="778" alt="task3-no-join" src="https://github.com/user-attachments/assets/19499d50-db85-4238-9c9b-c30084591147" />



### Task 3 Questions

**Task 3 – Question 1: Why does the main program wait when join() is used?**

The main program waits because join() blocks it until the download thread finishes, which prevents it from continuing too early.

**Task 3 – Question 2: What happens when join() is removed?**

When join() is removed, the main program does not wait, so "Main program continues." is printed before "Download completed."

**Task 3 – Question 3: In what situations is thread synchronization necessary?**

Thread synchronization is necessary when one part of a program depends on the result of another thread, such as waiting for a download to finish before using the file, or when threads access the same data.

---

## Task 4 – Managing Shared Resources Using Thread Locks

### Screenshots

**With lock**

<img width="1091" height="783" alt="task-with-lock" src="https://github.com/user-attachments/assets/3b4e5a73-b393-4acf-84c6-c7d0a5ce3e99" />


**Without lock**

<img width="1107" height="763" alt="task4-no-lock" src="https://github.com/user-attachments/assets/5ffe9bd1-6ea6-4224-b4b3-1879ac64b190" />


### Task 4 Questions

**Task 4 – Question 1: What is a shared resource?**

A shared resource is data or a variable that multiple threads can access, such as the counter variable in this program.

**Task 4 – Question 2: What is a race condition?**

A race condition occurs when multiple threads access and modify shared data at the same time, and the result depends on the timing of their execution.

**Task 4 – Question 3: What is the purpose of threading.Lock()?**

The purpose of threading.Lock() is to allow only one thread at a time to run the protected section of code.

**Task 4 – Question 4: What is a critical section?**

A critical section is the part of the code that accesses or modifies a shared resource. In this program, it is the counter += 1 statement.

**Task 4 – Question 5: Why is synchronization important when multiple threads access shared data?**

Synchronization is important because, without it, threads can overwrite each other's updates, which leads to incorrect or inconsistent results.

---

## Section VII – General Laboratory Questions

**Question 1: What is the difference between a process and a thread?**

A process is a running program with its own memory space. A thread is a smaller unit of execution inside a process, and threads within the same process share that process's memory.

**Question 2: What are the advantages of using multithreading?**

Multithreading allows a program to perform several tasks at the same time, uses resources more efficiently, and keeps applications responsive. Threads are also lighter than processes and can share data easily.

**Question 3: How does multithreading improve application responsiveness?**

Multithreading improves responsiveness by running slow tasks, such as downloads or file operations, in separate threads so the main program or user interface does not freeze.

**Question 4: What is the difference between concurrency and parallelism?**

Concurrency means multiple tasks make progress during the same time period, often by switching between them. Parallelism means multiple tasks run at the exact same moment on separate CPU cores.

**Question 5: Why is a lock necessary when multiple threads access shared data?**

A lock is necessary because it prevents multiple threads from changing the same data at once, which avoids race conditions and incorrect results.

**Question 6: What might happen if a thread is not properly synchronized?**

An unsynchronized thread may cause race conditions, lost updates, incorrect or inconsistent data, and unpredictable program behavior.

**Question 7: Can multiple threads execute simultaneously on a single-core processor? Explain.**

Not truly simultaneously. A single-core processor switches rapidly between threads, so they run concurrently but not in parallel.

**Question 8: How does the operating system manage kernel-level threads?**

The operating system kernel creates, schedules, and manages kernel-level threads directly. The scheduler decides which thread runs on which CPU core and for how long, and it handles switching between threads.

---

