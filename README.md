# real-time-task-scheduler
My goal :

              REAL-TIME TASK SCHEDULER
                       │
       ┌───────────────┼───────────────┐
       ↓               ↓               ↓
 Task Model       Scheduling       Monitoring
       │           Algorithms           │
       │               │                │
       │        ┌──────┼──────┐         │
       │        ↓      ↓      ↓         │
       │       EDF     RM     DM         │
       │                               ↓
       └──────────→ Scheduler ←──── Metrics
                       │
                       ↓
                  Execution
                       │
                       ↓
              Results / Timeline
                       │
                       ↓
                     GUI
