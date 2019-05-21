#SQL For Data Science#
##Week 1##

SQL is a non-procedual language where you cannot write complete applcations with it.

- Read
- Retrieve
- Write
- Update and Insert New Data

"Think before you Do".  Plan first, understand waht it is that you want to do and how the data relates to one another.   

Columns and **Records** (rows) 

**Data modelling** is what we use to organize information for multiple tables and how they relate to each other together.
    - Should always represent a real-world problem.

_Relational Model_  
    - Unstructured data (XML).  XML Data Enchanges
    - RDBMS
    - Scale up: need to add components to the box
    - Normalization: allows the data to stay in one place
    - SQL
    - Can create constraints
    -  ACID complient

_NoSQL (Not Only SQL) Model_   
    -  Big data    
    -  NoSQL is really a mechanism for storage and retrieval where it's not modeled in a tabular relational format
    -  MongoDB ??
    -  No redefined schema (very flexible)
    -  Handles unstructured data  
    -  Scaling out (aka Horizontal scaling):
    -  Non-Relational DB (no tables)
    -  Add additional nodes or clusters...far cheaper than hanging more stuff on a single box    
    -  
**Types of No SQL DBs**    
    - Doncument (MongoDB, CouchDB)
    - Column DBs (Apache Casandra)
    - Key_Value_Stores (Redis, Couchbase Server)
    - Cache Systems (Redis, Memcache)
    - Graph Databaes (Neo4J)

Operational DB v. Transactional DB   

Operational (Easy, logical, intuitive)
Transactional (Operational, hard to access and manipulate)

Building Blocks for Relational DB:
1.  Entities (Person, Place, Thing or Event - Unique and distinguishable   
2.  Attributes (Characteristics of the entity)   
3.  Cardinality - Relationship (describes the association amoung entities)
        - one to one
        - one to many
        - many to many   
    
**ER (Entity Relationship) Diagrams**:  visually shows links and processes between tables

**Primary Key**: A column or set of columns who's values uniquely identify each row in a table.
**Foriegn Keys**:  One or more colums that can be used together to identifyeach row in a table.  

**ER Diagram Notation:**
Chen:  1:M, M:N, 1:1 
Crows Foot:  Train Tracks  = 1, Crow's Foot = Many
UML Class Diagram Notation: 1.1 = 1, 1.* = Many 

##Retrieving Data with SELECT Statement   
SELECT what you want FROM where you want it.

SELECT * "give me everything"  
FROM tutrial.city_population 
LIMIT 10;   

##Creating Tables

CREATE TABLE Name of Table    
(
id          char(10)        PRIMARY KEY,   
color       char(10)        NOT NULL,   
size        char(5)         NOT NULL,   
price       decimal (8,2)   NOT NULL,   
desc        Varchar (750)   NULL   
)

You get the idea...

NULL values mean there is nothing there.  Empty strings still have a value, so they are not the same.   
PRIMARY KEYS cannot have NULL values.   
Every column needs a NULL defined.   

How do you get data into the table that you created?   
INSERT INTO Name of table    
VALUES ('1152'      
        ,'red'     
        ,'big'        
        ,'2.50'     
        ,NULL        
         );       
 Sublime HATES tables. 

##Creating Temporary Tables

Temp tables will be deleted when current session is terminated

CREATE TEMPORARY TABLE Name  AS 
(     
SELECT *    
FROM     
WHERE     
)

##Adding Comments
Remember WHAT you were doing and WHY   
Mute or commenting out   
Single Line:  --  Removes the entire line
Section: /*           /*


**SQLite Notes:**
1.  Open Terminal
2.  LS to see the dirs.
3.  CD to SQLite
4.  Enter sqlite3 to get the prompt
5.  .tables to see what's available.
























