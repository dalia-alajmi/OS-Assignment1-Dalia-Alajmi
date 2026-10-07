 # MY_WORK: Student Information & Development Log

## Student Information
- **Full Name**: Dalia Alajmi
- **Student ID**: 445052288
- **GitHub Repository**: https://github.com/dalia-alajmi/OS-Assignment1-Dalia-Alajmi
- **Video Demo Link**: * https://drive.google.com/file/d/1HeJsW6kifl9-_777PZSwP25OTWA76p3m/view?usp=share_link

---

## Development Log

- **2026-10-02**: Forked the repository, updated the student ID in SchedulerSimulation.java, and tested initial execution.
- **2026-10-03**: Added process priority feature (1-10) and updated ready queue display with ANSI colors.
- **2026-10-04**: Implemented context switch counter to track process switches and display total at end.
- **2026-10-05**: Added waiting time tracking using currentTime and lastExecutionTime logic.
- **2026-10-06**: Verified all features, checked final program outputs, and organized repository files.
---
## Reflection
### Question 1: What was the most challenging part of this assignment, and how did you overcome it?
The hardest part was calculating the waiting time correctly. Since processes run in small slices, I had to keep track of when each process last ran. I fixed this by using `lastExecutionTime` for each process and updating `currentTime` carefully during execution.
### Question 2: How does Round-Robin scheduling ensure fairness among processes?
It gives every process the exact same time quantum. If a process takes too long, it gets interrupted and sent back to the end of the queue, so no single process hogs the CPU.
### Question 3: What happens to context switching overhead when the time quantum is made extremely small or extremely large?
If it's too small, the CPU wastes a lot of time constantly switching between processes instead of doing actual work. If it's too large, it turns into FCFS, so short processes have to wait much longer.
### Question 4: How did implementing thread simulation help you understand OS concepts better than reading theory alone?
Writing the code made abstract concepts real. Seeing Java threads pause, run, and move through the queue showed me step-by-step how CPU scheduling actually works under the hood.
---
## Technical Answers
### Question 1: Explain the difference between a Process and a Thread in operating systems, with examples from your code.
A process is the main running program with its own memory space (like our Java program), while a thread is a smaller execution unit inside it. In our code, each task is run as a Java `Thread`.
### Question 2: How does the Ready Queue behave in your simulation, and what Java collection was used?
It works as a FIFO queue (first in, first out). We used `LinkedList` implementing the `Queue` interface (`Queue<Thread>`), adding processes with `add()` and pulling them with `poll()`.
### Question 3: Describe the Thread Lifecycle in Java and identify where each state transition occurs in your code.
- **New**: when created with `new Thread()`.
- **Runnable**: when `start()` is called.
- **Timed Waiting**: when `Thread.sleep()` is running.
- **Terminated**: when the thread finishes execution and passes `join()`.
### Question 4: Give two real-world application examples where Round-Robin scheduling is used and explain why.
1. **Desktop OS (Windows/Linux)**: to keep the interface smooth and responsive for the user while running background tasks.
2. **Web Servers**: to handle incoming requests fairly without letting one heavy request delay others.
