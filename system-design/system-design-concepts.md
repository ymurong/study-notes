- [Consistent Hashing](#consistent-hashing)
- [OOP](#oop)
- [SQL vs NOSQL](#sql-vs-nosql)
  - [SQL](#sql)
  - [NOSQL](#nosql)
    - [Column Based (OLAP)](#column-based-olap)
    - [KV](#kv)
    - [Dictionary](#dictionary)
    - [Index](#index)
    - [Graph](#graph)
  - [Selection of SQL and NoSQL databases](#selection-of-sql-and-nosql-databases)
    - [Internal use of management-oriented systems](#internal-use-of-management-oriented-systems)
    - [High traffic system](#high-traffic-system)
    - [Log type system](#log-type-system)
    - [Search system](#search-system)
    - [Transaction-based systems](#transaction-based-systems)
    - [Off-line computing](#off-line-computing)
    - [Real-time computing](#real-time-computing)


# Consistent Hashing
1. Classical Hashing: hash(IP)%N -> Add/Remove Server -> Key Mapping changed a lot 
2. Consistent Hashing: hash(IP)%2^32 -> Key in between Target Servers -> Add server only influence key mapping that is between its adjacent servers.
3. Issue: data skewness
   - create virtual server nodes 
   - mapping become complex: key -> virtual node -> physical node


# OOP 
- Inheritance
- Encapsulation
- Polymorphism
  - dynamic polymorphism (runtime)
    - Method overriding
  - static polymorphism
    - Method overloading
    - 
# SQL vs NOSQL
## SQL
- ACID properties
  - 原子性（atomicity，或称不可分割性
    - all or nothing !
  - 一致性（consistency)
    - data consistent (payment transaction, guaranteed by atomicity and business logic)
  - 隔离性（isolation，又称独立性)
    - transactions are isolated between each other (isolation levels)
      - read uncommitted (dirty read, unrepeated read, phantom read)
      - read committed (unrepeated read, phantom read)
      - repeatable read (phantom read)
      - serializable (lowest performance)
    - possible problems
      - dirty read: transaction A reads uncommited transactions B's modification
      - unrepeated read: transaction A reads different results (changed by transaction B)
      - phantom read: transaction A changed a whole table while transaction B add one row, then transaction A finds that we had one unchanged added row
  - 持久性（durability）
    - once committed, in database forever
- Referential Integrity (Normalization)
- Transaction based 
  
## NOSQL
structured/semi-structure

### Column Based (OLAP)
- usecases: suitable for OLAP system, message history
- examples: hbase, bigtable, duckdb

### KV
- really high performance
- usecases: realtime ranking, fans followers, shopping cart, session
- examples: redis, cassandra

### Dictionary 
- usecases: documents, xml, json
- examples: mongodb, couchdb
- only one document atomicity, only read committed isolation

### Index
- inverted index: document searching/ranking
- examples: elastic search, solr

### Graph
- advantage: full acid support
- usecases: social network, recommendation
- examples: neo4j, titan


## Selection of SQL and NoSQL databases

- Data volume
- Concurrency
- Real-time performance
- Consistency requirements
- Read and write distribution and type
- Security
- Operation and maintenance costs

Common software system database selection references are as follows.

### Internal use of management-oriented systems
Such as operation system, data volume is small, concurrency is small, the first choice to consider relational

### High traffic system
Such as e-commerce single product page, the back office to consider the choice of relational, the front office to consider the choice of memory type

### Log type system
Consider columnar type for raw data, and inverted index for log search

### Search system
For example, the site search, non-universal search, such as product search
- the back office to consider the choice of relational
- the front office to consider the choice of inverted index

### Transaction-based systems
Such as inventory, transactions, bookkeeping, consider choosing relational + cache + consistency protocols

### Off-line computing
Consider choosing columnar or relational type for large amount of data analysis

### Real-time computing
Such as real-time monitoring, you can consider choosing in-memory or columnar database

In design practice, based on the requirements, business-driven architecture, regardless of the choice of RDB/NoSQL/DRDB, must be demand-driven, the final data storage solution is bound to be a comprehensive set of various trade-offs.
