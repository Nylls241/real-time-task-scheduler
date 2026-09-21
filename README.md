# real-time-task-scheduler
## Architecture (Goal)

```text
              REAL-TIME TASK SCHEDULER
                       │
       ┌───────────────┼───────────────┐
       ↓               ↓               ↓
 Task Model       Scheduling       Monitoring
       │           Algorithms           │
       │               │                │
       │        ┌───────┼───────┐       │
       │        ↓       ↓       ↓       │
       │       EDF?      RM?      DM?   │
       │                                ↓
       └──────────→ Scheduler ←───── Metrics
                       │
                       ↓
                  Execution
                       │
                       ↓
              Results / Timeline
                       │
                       ↓
                      GUI
```
