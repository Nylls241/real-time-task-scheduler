# MVP Specifications — Real-Time Task Scheduler

## 1. Project Overview

The goal of this project is to build a minimal real-time task scheduler capable of managing tasks and selecting the most appropriate task to execute based on defined constraints.

The MVP focuses on implementing the core scheduling logic before adding advanced features such as persistence, parallel execution, or optimization.

---

# 2. MVP Goals

The MVP must allow users to:

- Create tasks
- Define task properties
- Store tasks in memory
- Select the next task to execute
- Display scheduling results

---

# 3. Functional Requirements

## 3.1 Create Tasks

### Description

The system must allow users to create new tasks.

### Task information:

Each task must contain:

- Unique identifier
- Name
- Duration
- Priority
- Deadline

### Example:

```

Task:
{
id: 1,
name: "Process network packet",
duration: 50ms,
priority: HIGH,
deadline: 200ms
}

```

---

## 3.2 Define Task Duration

### Description

Each task must have an estimated execution duration.

### Requirements:

- Duration must be expressed in milliseconds.
- Duration must be a positive value.
- The scheduler must use duration information when selecting tasks.

Example:

```

Duration: 100ms

```

---

## 3.3 Define Task Priority

### Description

Each task must have a priority level.

### Priority levels:

```

HIGH
MEDIUM
LOW

```

### Requirements:

- Higher priority tasks should be considered first.
- Priority must influence the scheduling decision.

Example:

```

Task A → HIGH
Task B → LOW

```

The scheduler should prefer Task A.

---

## 3.4 Define Task Deadline

### Description

Each task may have a deadline representing the maximum acceptable execution time.

### Requirements:

- Deadline is expressed in milliseconds.
- Tasks close to their deadline should receive higher importance.
- The scheduler must consider deadline constraints.

Example:

```

Deadline: 500ms

```

---

# 4. Scheduling Requirements

## 4.1 Select Next Task

### Description

The scheduler must choose the next task to execute from the available tasks.

### MVP scheduling strategy:

The scheduler selects tasks according to:

1. Priority
2. Deadline urgency
3. Shortest duration

Decision order:

```

Highest priority
↓
Closest deadline
↓
Shortest execution time

```

Example:

```

Task A:
Priority: HIGH
Deadline: 500ms
Duration: 100ms

Task B:
Priority: LOW
Deadline: 50ms
Duration: 20ms

Selected task: Task A

```

---

# 5. Display Results

## Description

The scheduler must display the scheduling decision.

The output should include:

- Selected task
- Task properties
- Reason for selection

Example:

```

Next task selected:

ID: 3
Name: Network packet processing
Priority: HIGH
Duration: 50ms
Deadline: 200ms

Reason:
Highest priority task.

```

---

# 6. Non-Functional Requirements

## Performance

The scheduler should:

- Handle multiple tasks in memory.
- Select the next task efficiently.
- Keep scheduling decisions deterministic.

## Code Quality

The project should:

- Use modern C++ practices.
- Separate responsibilities.
- Include documentation.
- Include unit tests.

---

# 7. MVP Limitations

The MVP does not include:

- Multithreading
- Real operating system integration
- Persistent storage
- Graphical interface
- Distributed scheduling
- Machine learning optimization

These features may be considered for future versions.

---

# 8. Future Improvements

Possible extensions:

- Real-time scheduling algorithms:
  - Earliest Deadline First (EDF)
  - Rate Monotonic Scheduling (RMS)

- Task dependencies
- CPU simulation
- Multicore scheduling
- Performance benchmark
