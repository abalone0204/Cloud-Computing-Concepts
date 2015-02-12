# Week 1

## Question

You shall answer these questions after week-1.

- Why is cloud computing popular today?

- What is different in cloud computing compared to previous generations of distributed systems?

- How does one program in MapReduce?

- How does the MapReduce system schedule jobs?


## Why "Cloud" become so popular?

- Hype!

- It's saving money and time.

> Example
> - AWS()
> - Google Cloud Computing
> - And many others.

- The `Cloud` save the time we deploy our application, and with those `cloud services` we don't actually to maintain our own realistic machine!

## What is a cloud

> Cloud = Lots of storage + compute cycles nearby

- Notice that it's a working answer for this course.


- The topology structure of Cloud Computing(text):Core switch > many switch > many racks > many servers.

> Just a simpified note, please refer to the course to see the gragh one.

## History of Cloud computing

- The conceCloud computing exists for decades.

- Since 1980, PC makes clustering computer and setting network become easier, and all of the progress culminated in now day cloud computing technique.
 
- Moore Law: (The doubling periods)
  
  - Storage: 12 months.

  - Bandwidth: 9 months

  - CPU compute capacity: 18 months

- Today's cloud computing is similiar to "Data processing industry" era in the past.


## Intro what's new in today's clouds

- There are 4 features new in today's clouds comparing to  distributed computing in the past.

  - Massive scale

  - On-demand access

  - Data-intensive Nature

  - New Cloud Programming Paradigms

## Intro : New aspects of clouds

- On-demand access: *aas classification
  
  - pay as what you use (AWS EC2)

  - Haas(Hardware as a service): It may have some security consideration using it.

  - Iaas(Infrastructure as a service): Providing you a VM and you can login do something awesome.

  - Paas(Platform as a service): Comparing to `Iaas` You don't have authority to login the vm, but you can run your codes on cloud machine(Like google app engine). And it can autoscale your application.
  
  - Saas(Software as a service): Its definition is commonly broad, but none of above can exactly consider it as Saas. For instance: Gmail, google docs...etc.

- Data-intensive Computing

  - The focus shifts from computation to the data.

- New cloud programming paradigms

  - There are many things you can refer in the course's ptt.(Google MapReduce)

  - In conclusion those programming pradigms make you query and store data more fairly quickly than before.

  - This is just like the programming languae become more and more easier to learn.


## Intro: Economics of clouds

- Here's the question many people might ask: Clouds are money saver, aren't they?

- But the real question is : Shall you own your cloud (private cloud) or just use public cloud?

- Short-term  service: Use public cloud.

- Long-term service: Own your private cloud.

- Check the calculation in the course. It's not about computer science, it's more about cost.



----

## MapReduce Paradigm - First level

- Now we can having fun with mapreduce.

- You will learn what it is and how it works.

### Basic Level

- What is MapReduce?

- It's borrow from Functional Language(e.g., Lisp)

- Map + Reduce

- Map:

```
map square (1 2 3 4)

Output  (1 4 9 16)
```
- Reduce(there is the tricky part):

```
reduce + (1 4 9 16)
=> (+16(+9(+4 1)))
Output: 30
```

- But you may wonder why we need map and reduce to handle this? Isn't the origin way nice enough? Check the example beside.

> Functional programming's wiki
> http://en.wikipedia.org/wiki/Functional_programming

### Example: Word Count

- How to find all ther word count of each word appear across entrie wiki?

- Map:

- Process individual records to generate intermediate key and value pairs. 

- Here is our first example text set:


> Welcome everyone
> Hello everyone

Key| Value 
---------| ------------ 
Welcome | 1
everyone | 1
Hello | 1
everyone | 1

- `Map` can parallelly process individual records to generate intermediate key/value pairs.

- We have duplicated `everyone` now, so we can apply the map task's result to `Reduce`, and get the record for per-key based below.

Key| Value 
---------| ------------ 
Welcome | 1
Hello | 1
everyone | 2

- If there is a little confusing, fee free to check ther course's video.

- And if you're not so familiar how reduce and map works, proffessor provide a simple and clear example for us.

----

#### Question
> A given Mapreduce program has the Map phase generate 100 key-value pairs with 10 unique keys. How many Reduce tasks can this program have when at least one Reduce task will certainly be assigned no keys when a hash partitioner is used (select all answers that are correct)?"

- [ ]A.  3

- [ ]B.  11

- [ ]C. 50

- [ ]D. 101


#### Solution:

The answers are B, C, D.

Since the unique keys' number is 10. We must have at least 10 reduce task. And at least one reduce task has null key.

So... there is a little bit stupid:

- A: 3 < 11 -> Wrong!

- B, C, D >=  11 -> Bingo!

----

### Hadoop 

- You can check proffessor's demo codes during the course.

(Including the map and reduce functions.)

- I provide some refers about Hadoop for you!

- See the official page: [http://hadoop.apache.org/](http://hadoop.apache.org/)


----

## MapReduce Paradigm - Examples

- Just watch the video codes, 

----

## Mapreduce Scheduling

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


## MapReduce - Fault-tolerance

- NM heartbeats to RM
  
  - If server fail, RM will let all affected AMs know, and AM takes action.

- NM keeps tracks of each task running at its server

- AM heartbeats to RM

  - On failure, RM restarts AM, which then syncs up with running task

- RM failure
  
  - Use old checkpoints and bring up secondary RM

- Speculative execution:(Handling by AM) Copy the slowest task on another server, if it runs faster than the original one, kill the original one and get the result completed first. So, it's actually a **replicate execution**.

- Locality:



## Interview with Sumeet Singh(Senior Director of Big Data and Cloud Platform in Yahoo! Inc)

- How do Yahoo! define cloud computing?

  - It's first thinking about scale.(Billions of users).

- Future will go more and more insteresting.

- 













