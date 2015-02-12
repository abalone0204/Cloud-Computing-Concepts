## 1.7 MapReduce Paradigm - First level

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