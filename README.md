# Pyspark-Learning
This Repository contains sample codes which l learnt from the linkedin course: "Apache PySpark by Example"


Lesson 1.1
	Apache Spark consists of
		
	i) Spark Core API - Take cares of Task Scheduling, Memory Management, Fault Recovery and Interacting with storage systems. Primarliy written in scala, but can be accessed by Java, Python, R and SQL.

	ii) Important functionalities include Spark SQL, Streaming, MLlib and GraphX.
		
Lesson 1.2
	Pyspark is python wrapper around spark(which is written in scala)
	
Lesson 1.4 
	
	i) Creating Spark session is the first step of any spark application.
	ii) With Spark 2.0, a spark session can access all of spark's functionality through a single unified point of entry.
	iii) When you start your spark session in python, Pyspark uses PY4G to launch java virtual machine and creates a java spark context. All PY4G allows python programs to dynamically access java objects in java virtual machine.


Lesson 1.5 Partitions, transformations, lazy evaluations, and actions
    
	i) Spark is a distributed system. This means that if we want the workers to work in parallel, Spark needs to break the data into chunks or partitions. A partition is a collection of rows from your dataframe that sits on one machine in your cluster. So a data rames partition is how the data is physically distributed across the cluster of machines during execution.

	ii)Transformations are a core data structure in Spark, and they can't be changed once they've been created. So the instructions that we use to modify the data frame are known as transformations. This could be a filter operation, or a distinct operation, where you only get the unique values in a certain column. You'll find that when we perform transformation operations, nothing seems to happen. Spark doesn't act on transformations until we perform something called actions.

	iii)when an operation is performed on your data, Spark doesn't work on modifying the data straight away. Instead, it builds a plan of transformations that will be performed on the data. This waiting until the last moment to do the work is known as a lazy evaluation. 	It's really helpful, because it allows Spark to create a streamlined plan, allowing it to run as efficiently as possible across the cluster. This makes really good sense for big data jobs.

	Example
	Let's say you have a log file with millions of rules of data. You then decide to filter all of the ones that were identified by a certain type of error. And then finally, you call a function to fetch only one of those filtered rules. What would Spark's lazy evaluation do? Well, it just needs to find the first occurrence of the type of error message in any of the partitions, because all you wanted was one rule. So let's compare that with what would have happened if you didn't use the lazy evaluations. Well you'd start off with the log file, you then filter by errors in all of the partitions, you then store these intermediate results somewhere, even though all you were interested in was a single rule with a certain type of error. 
	
	iv) Actions include view, collect and store.
	
	
	
Lesson 2 - Installtions

Lesson 3.1
	i) Dataframe API - High level
	ii) RDD - Lowlevel API
	iii) Python does not support Dataset API, but most of its functionalitites are available in Dataframe API.
	
**From Lesson 3.2 See jupyter notebook.**
