solution of exercise of Mining of Massive Datasets
====================================================

## chapter 2( Large-Scale File Systems and Map-Reduce)
### section 2.3
**Exercise 2.3.1**: Design map-reduce algorithms to take a very large ?le of integers and produce as output:<br>
(a) The largest integer.<br>
solution:let **s** is set of integer that is input<br>the map function:for each integer in **s** such t,produce key-value pair (1,t)<br>
the reduce function:input of this task is pair thet this key is 1,and associated value is list[t1,t2,...ti,...,tn] that each ti is value of pair of output of map task.output of reduce task is pair(1,max{t1,t2,....,tn})<br>
notice that max is a associative and commutative function,we can produce only one pair (1,max{t1,...tm}) in map task,that m is number of integer that input to map task.
(b) The average of all the integers.<br>
solution:<br>
the map function:for each integer in s such t,produce key-value pair (1,t)<br>
the reduce function:input of this task is pair thet this key is 1,and associated value is list[t1,t2,...ti,...,tn] that each ti is value of pair of output of map task.output of reduce task is pair(1,averge{t1,t2,....,tn})
<br>(c) The same set of integers, but with each integer appearing only once.
<br>solution:<br>
the map function:for each integer in s such t,produce key-value pair (t,t)<br>
reduce function:For each key t produced by any of the Map tasks, there will be one or more key-value pairs (t,t). The Reduce function turns (t,[t,t,...,t]) into (t',t'), so it produces exactly one pair (t,t) for this key t.<br>
(d) The count of the number of distinct integers in the input.<br>


