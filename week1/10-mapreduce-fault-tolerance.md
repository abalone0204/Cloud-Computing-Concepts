## 1.10 MapReduce - Fault-tolerance

- NM heartbeats to RM
  
  - If server fail, RM will let all affected AMs know, and AM takes action.

- NM keeps tracks of each task running at its server

- AM heartbeats to RM

  - On failure, RM restarts AM, which then syncs up with running task

- RM failure
  
  - Use old checkpoints and bring up secondary RM

- Speculative execution:(Handling by AM) Copy the slowest task on another server, if it runs faster than the original one, kill the original one and get the result completed first. So, it's actually a **replicate execution**.

- Locality