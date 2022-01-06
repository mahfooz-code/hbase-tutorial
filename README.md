# hbase-tutorial
Explain What is HBase?
HBase is a column-oriented database management system which runs on top of HDFS 
(Hadoop Distribute File System). 
HBase is not a relational data store, and it does not support structured query 
language like SQL.

In HBase, a master node regulates the cluster and region servers to store portions of the tables and operates the work on the data.

#Explain why to use HBase?

1) High capacity storage system 
2) Distributed design to cater large tables 
3) Column-Oriented Stores 
4) Horizontally Scalable 
5) High performance & Availability 
6) Base goal of HBase is millions of columns, thousands of versions and billions of rows 
7) Unlike HDFS (Hadoop Distribute File System), it supports random real time CRUD operations

#Mention what are the key components of HBase?

1) Zookeeper: It does the co-ordination work between client and HBase Maser 
2) HBase Master: HBase Master monitors the Region Server 
3) RegionServer: RegionServer monitors the Region 
4) Region: It contains in memory data store(MemStore) and Hfile. 
5) Catalog Tables: Catalog tables consist of ROOT and META

#Explain what does HBase consists of?

1) HBase consists of a set of tables 
2) And each table contains rows and columns like traditional database 
3) Each table must contain an element defined as a Primary Key 
4) HBase column denotes an attribute of an object

#Mention how many operational commands in HBase?

There are mainly Five types of Operational commands in HBase:

1) Get 
2) Put 
3) Delete 
4) Scan 
5) Increment

#Explain what is WAL and Hlog in HBase?

WAL (Write Ahead Log) is similar to MySQL BIN log; it records all the changes 
occur in data. 
It is a standard sequence file by Hadoop and it stores HLogkey’s. 
These keys consist of a sequential number as well as actual data and are used to 
replay not yet persisted data after a server crash.
So, in cash of server failure WAL work as a life-line and retrieves the lost 
data’s.

#When you should use HBase?

1) Data size is huge: When you have tons and millions of records to operate 
2) Complete Redesign: When you are moving RDBMS to HBase, you consider it as a complete re-design then mere just changing the ports 
3) SQL-Less commands: You have several features like transactions; inner joins, typed columns, etc. 
4) Infrastructure Investment: You need to have enough cluster for HBase to be really useful

#In HBase what is column families?

Column families comprise the basic unit of physical storage in HBase to which features like compressions are applied.

# Explain what is the row key?

Row key is defined by the application. As the combined key is pre-fixed by the rowkey, it enables the application to define the desired sort order. It also allows logical grouping of cells and make sure that all cells with the same rowkey are co-located on the same server.

# Explain deletion in HBase? Mention what are the three types of tombstone markers in HBase?

When you delete the cell in HBase, the data is not actually deleted but a tombstone marker is set, making the deleted cells invisible. HBase deleted are actually removed during compactions.

Three types of tombstone markers are there:

Version delete marker: For deletion, it marks a single version of a column
Column delete marker: For deletion, it marks all the versions of a column
Family delete marker: For deletion, it marks of all column for a column family

#Explain how does HBase actually delete a row?

In HBase, whatever you write will be stored from RAM to disk, these disk writes are immutable barring compaction. During deletion process in HBase, major compaction process delete marker while minor compactions don’t. In normal deletes, it results in a delete tombstone marker- these delete data they represent are removed during compaction.

Also, if you delete data and add more data, but with an earlier timestamp than the tombstone timestamp, further Gets may be masked by the delete/tombstone marker and hence you will not receive the inserted value until after the major compaction.


#Can the region server will be located on all DataNodes?

Yes, Region Servers run on the same servers as a DataNodes

#Name the filter which accepts the page size as the parameter in HBase

A filter named PageFilter accepts the page size as the parameter.

This document has been composed with the instant HTML converter tools.

#What is the use of HBase HMaster?

Main responsibilities of a master are:

Coordinating the region servers
Admin functions
28) Which technique can you use in HBase to access HFile directly without the help of HBase?

To access HFile directly without using HBase, we use HFile.main() method.






