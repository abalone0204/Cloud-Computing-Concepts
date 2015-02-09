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

## MapReduce Paradigm

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

Word(Key)| Count(Value) 
---------| ------------ 
Welcome | 1
Hello | 1
everyone | 2






















