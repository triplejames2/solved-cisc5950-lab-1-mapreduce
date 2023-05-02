Download Link: https://assignmentchef.com/product/solved-cisc5950-lab-1-mapreduce
<br>
<span class="kksr-muted">Rate this product</span>

Based on our examples, we will develop our own MapReduce program to analysis a simple log file. The following figure shows the structure of the log file.

Each line is a record of visit, which consists of IP Address, Time, Type of HTTP Request, Requested File, HTTP Version and Status, etc.

Example Programs

We have provided two examples that related to this lab.• logstat: It counts the number of visits for each IP address in the log file.• logstat2: It counts the number of visits for each IP address in the same hour.

As discussed in the lectures, MapReduce programming framework seperates the data and op- eration (two stages). It uses Hadoop Stream, which represents by sys.stdin in Python and Writable, Text in Java.

Figure 1: Map Phase of logstat in Python

1

CISC 5950, Spring 2022

Big Data Programming

Figure 2: Map Phase of logstat in Java

Figure 3: Reduce Phase of logstat in Python

In Map phase, we have to process the raw files and extract the related information, line and IP.

In the Reduce phase, we start counting the records based on the same IP addresses. After that, we can sort the result and print it out. As Fig. 5 and 6 present, the Map Phase for logstat2 is different than the previous version since we need to consider the time. Since we have pro- cessed data at Map Phase, the intermediate data of Map is already at the granularity of a hour. Therefore, the Reduce Phase is the same as logstat.

Lab 1 Assignment: Part 1 and 2

The given programs of logstat and logstat2 were written in both JAVA and Python. Lab 1 consists of the following two parts.

1. Output the top-3 IP addresses with the granularity of an hour • You should read the two examples.

2

CISC 5950, Spring 2022

Big Data Programming

Figure 4: Reduce Phase of logstat in Java

Figure 5: Map Phase of logstat2 in Python

• Develop your code based on examples. The program may take more than one round of MapReduce.

2. Make your program like a database search

<ul>

 <li>Your program should be able to accept parameters from users, such as 0-1, which means from time 00:00 to 01:00, and output the top-3 IP addresses in the given time period.</li>

 <li>Run it along with three other examples, WordCount, Sort, Grep, at the same time, and test fair and capacity schedulers.</li>