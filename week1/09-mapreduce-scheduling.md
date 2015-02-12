## 1.9 Mapreduce Scheduling

- Map can be run parallelized easily, since each map task is independent from the other.

- Reduce task should be run after all map task done, since the resuce task will run on each key once.That's call "barrier".

- But it's not true all the time, if we can maintain the result of map task and run reduce task for the rest of all, the barrier would be solved.

### Internal workings of MapReduce

- Take YARN as example:

- YARN(Yet Another Resource Negotiator)

  - Treat each server as a collection of containers

  - Has 3 main components:

    1. Global Resource Manager(RM) -> Scheduling

    2. Per-server Node Manager(NM) -> Daemon and server-specific functions

    3. Per-application(job) Application Master(AM) -> Container negotiation with RM and NMs and detecting task failures of the job.

(About 11:00, see the flow chart of "How a job gets a container" will help you a lot.)