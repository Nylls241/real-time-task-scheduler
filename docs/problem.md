# Problem Description — Real-Time Task Scheduler

## 1. Introduction

Modern computer systems execute a large number of tasks that compete for limited resources such as CPU time.

When multiple tasks are available, the system must decide:

- Which task should execute first?
- How long should it execute?
- How can deadlines be respected?
- How can resources be used efficiently?

This decision-making process is known as **task scheduling**.

The goal of this project is to explore and implement a simplified real-time task scheduler capable of selecting the most appropriate task according to predefined constraints.

---

# 2. The Scheduling Problem

## Definition

Scheduling is the process of assigning execution order to a set of tasks.

Given a collection of tasks, a scheduler must determine the order in which these tasks should run.

Each task can have different characteristics:

- Execution duration
- Priority level
- Deadline
- Resource requirements

The challenge is to find an execution order that optimizes one or several objectives:

- Minimizing waiting time
- Respecting deadlines
- Maximizing system efficiency
- Giving priority to critical tasks

---

## Example

Imagine a system with three tasks:

```

Task A:
Priority: HIGH
Duration: 50ms
Deadline: 200ms

Task B:
Priority: LOW
Duration: 100ms
Deadline: 500ms

Task C:
Priority: MEDIUM
Duration: 30ms
Deadline: 150ms

```

The scheduler must decide which task should execute first.

A simple solution could prioritize:

1. High priority tasks
2. Tasks with urgent deadlines
3. Short execution times

The selected order will directly impact system performance.

---

# 3. Scheduler Definition

## What is a Scheduler?

A scheduler is a software component responsible for managing the execution of tasks.

Its main responsibility is:

> Select the next task to execute among all available tasks.

A scheduler typically performs the following operations:

1. Maintain a list of available tasks
2. Evaluate task characteristics
3. Apply a scheduling algorithm
4. Select the next task
5. Assign CPU execution time

---

## Scheduler Components

A basic scheduler contains:

### Task Queue

Stores tasks waiting for execution.

Example:

```

Waiting Tasks:

Task 1
Task 2
Task 3

```

---

### Scheduling Algorithm

The decision-making logic used to choose the next task.

Example:

```

Input:
List of tasks

Algorithm:
Compare priorities and deadlines

Output:
Selected task

```

---

### Execution Manager

Responsible for executing the selected task and updating the system state.

---

# 4. Importance of Real-Time Systems

## Definition

A real-time system is a computer system where correctness depends not only on producing the correct result, but also on producing it within a required time constraint.

In real-time systems:

```

Correct result + Correct timing = Correct behavior

```

---

## Examples of Real-Time Systems

Real-time scheduling is critical in many domains:

### Automotive Systems

Examples:

- Autonomous driving
- Anti-lock braking systems
- Engine control systems

A delayed decision can create safety risks.

---

### Aerospace Systems

Examples:

- Flight control systems
- Satellites
- Space exploration systems

Tasks must execute within strict timing constraints.

---

### Embedded Systems

Examples:

- Industrial robots
- Medical devices
- IoT devices

The system must react quickly to external events.

---

## Why Scheduling Matters

A poor scheduling strategy can cause:

- Missed deadlines
- Poor performance
- Resource waste
- System instability

A good scheduler improves:

- Responsiveness
- Predictability
- Resource utilization

---

# 5. Scheduling Algorithms Overview

Different scheduling algorithms exist depending on system requirements.

---

## 5.1 First Come First Served (FCFS)

### Principle

Tasks are executed in the order they arrive.

Example:

```

Arrival order:

Task A
Task B
Task C

Execution:

A → B → C

```

### Advantages

- Simple implementation
- Fair

### Limitations

- Important tasks cannot bypass older tasks
- Poor for real-time systems

---

## 5.2 Shortest Job First (SJF)

### Principle

The task with the shortest execution time is selected first.

Example:

```

Task A: 100ms
Task B: 20ms
Task C: 50ms

Execution:

B → C → A

```

### Advantages

- Reduces average waiting time

### Limitations

- Long tasks may wait indefinitely

---

## 5.3 Priority Scheduling

### Principle

Tasks are executed according to their priority.

Example:

```

HIGH
MEDIUM
LOW

```

### Advantages

- Critical tasks execute first
- Simple to understand

### Limitations

- Low priority tasks may starve

---

## 5.4 Earliest Deadline First (EDF)

### Principle

The task with the closest deadline is executed first.

Example:

```

Task A deadline: 500ms
Task B deadline: 100ms

Execution:

B → A

```

### Advantages

- Efficient for real-time systems
- Handles deadlines explicitly

### Limitations

- Requires accurate timing information

---

## 5.5 Rate Monotonic Scheduling (RMS)

### Principle

Tasks with shorter periods receive higher priority.

Commonly used in periodic real-time systems.

Example:

```

Task A:
Runs every 10ms → High priority

Task B:
Runs every 100ms → Lower priority

```

### Advantages

- Predictable
- Mathematically analyzable

### Limitations

- Mainly designed for periodic tasks

---

# 6. Project Scope

This project implements a simplified real-time scheduler.

The MVP focuses on:

- Task creation
- Task properties management
- Scheduling decision
- Result visualization

Future versions may include:

- EDF algorithm
- Multithreading
- CPU simulation
- Task dependencies
- Performance benchmarking

---

# 7. Conclusion

Task scheduling is a fundamental problem in computer systems.

A scheduler must make efficient decisions while respecting constraints such as priority and deadlines.

This project provides a practical exploration of scheduling concepts and real-time system principles through a simplified C++ implementation.