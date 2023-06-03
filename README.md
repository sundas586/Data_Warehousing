# Data_Warehousing

## fact table vs Dimention table :

- The fact table is where other than id's , you store factual data/ numeric data, by factual data it means that the values that keeps changing, like how many sales today for this product, or how many transactions in a day at this ATM, so this type of data is transactional and the values keeps changing each day for each BK.
- The dimenson table on the other hand stores descriptive data, that is the name of the product or the name of the Bank of this ATM, its address or branch number, now this descriptive data will remain same for each BK and will not change frequently, so this less frequently changing data we save in dimension table and join kdimention and fact table when need to know some info.


The data warehouse is a system which is used for analysis and reporting of data collected from operational systems and different data sources.

![a](https://user-images.githubusercontent.com/33677647/204094016-512b470a-5f76-4e55-b9cb-7d2c43b47ad5.JPG)
![b](https://user-images.githubusercontent.com/33677647/204094020-7ebaee07-2378-4047-975a-d00870394b07.JPG)
![c](https://user-images.githubusercontent.com/33677647/204094022-f30a6a5c-56c4-4841-80eb-eef04900c7f6.JPG)


Any good company plans a idea (lets see from last years Eid sale, which kind of item was sold out the most ? )
- So they plan idea
- gather data
- analyze it
- in action
- gets big profit out of investment

![a](https://user-images.githubusercontent.com/33677647/204095173-97615fce-bfff-41d8-8b0e-8dd8741a8954.JPG)

![1](https://user-images.githubusercontent.com/33677647/204098621-244c0485-b852-4fc3-8ea6-7858dd1aec57.JPG)
![2](https://user-images.githubusercontent.com/33677647/204098624-9875f987-f125-4d61-8f52-e91cdc595a18.JPG)

**we use data warehousing technique to transform data** :
- means when we get data from different sources (e.g different product's data stored in different different RDMS, like MS SQL server, Oracle, MariaDB, etc) we integrate them in one place and clean them. <br/>
- when we need data for bussiness analysis, we fetch it from Data Warehouse and visualize them.
- DWH technique makes visualization easy.
 
- Data lakes accept unstructured data
- **Data warehouses only accept structured data from multiple sources and Make them all related together as one**.
- Databases perform best when there's a single source of structured data and have limitations at scale.
- 
![1](https://user-images.githubusercontent.com/33677647/204098919-abfaeaed-1c12-4ee7-82b0-a79ccd702434.JPG)

End User --> BI analysts <br/>

## ETL

The process of extraction of operational data , Transforming it, loadding into your DWH is called **ETL**.
The ETL can be stored in any RDMS as a DWH, where all data can be inter-linked using shcema

**What is operational database system ?**<br/>
operational database systems are oriented towards real-time, transactional operations, it is collection of data of multiple sources. It is updated each second.<br/>
We do not add each and every real time data (e.g transactions) to dataware house. because we dont want our anaalysis to be affected <br/>
BUT!!!<br/>
When ever operational data is needed to be used for BI analysis, it has to go through DWH first.


- Operational data is extracted,transformed and loaded to DWH.
- then it can be used by End Users for visualiztion with help of **OLAP (Online Analytical processing).**
- Later the data can be used for visualiztion using PowerBI, Tablue, etc.

The data once stored in DWH is always available to endusers,it can be modified but not deleted, it acts as a backup record for data analysis, they can even access 10 years old data using OLAP.

![1](https://user-images.githubusercontent.com/33677647/204101053-d9a19933-096e-484e-95f1-9c5d38386462.JPG)
![1](https://user-images.githubusercontent.com/33677647/204106625-320b182b-cfab-4a6e-b4c5-3becd478756b.JPG)
![3](https://user-images.githubusercontent.com/33677647/204107229-10a0ebb0-cc47-45de-9f92-57fe72dc42f3.JPG)
![2](https://user-images.githubusercontent.com/33677647/204107231-1708d75d-aa5b-469b-a24a-e3dee01a63b3.JPG)
![1](https://user-images.githubusercontent.com/33677647/204107237-385d43e0-54f4-4939-b67e-aba753438f54.JPG)
![1](https://user-images.githubusercontent.com/33677647/204112341-4967956b-dd19-4025-acd0-cc4a4a7e7699.JPG)
![3](https://user-images.githubusercontent.com/33677647/204112370-605f7f07-51b8-4c21-953a-65ddf4f56b15.jpg)
![4](https://user-images.githubusercontent.com/33677647/204112348-3d82171f-710d-4f46-bd52-e10f62496080.JPG)

A data mart is a subset of a data warehouse focused on a particular line of business, department, or subject area. Data marts make specific data available to a defined group of users, which allows those users to quickly access critical insights without wasting time searching through an entire data warehouse.<br/>
Data marts are like sub-DWH(childs)<br/>
As to keep the data of one dpt. private from other dpt, also it takes less storage.<br/>
we make small DWHouses for each dpt.<br/>
But the real DWH keeps the data of all these DM(small DWH).<br/>

![1](https://user-images.githubusercontent.com/33677647/204112462-336f75c9-3803-4c8b-95e3-12bf9e9e746e.png)
![2](https://user-images.githubusercontent.com/33677647/204112473-3d36420b-1f2b-46a7-a379-6ef3486c9420.png)
![88](https://user-images.githubusercontent.com/33677647/204112506-638e40f7-dd99-48f8-83c5-821ae5ef72b4.png)
![4](https://user-images.githubusercontent.com/33677647/204112512-e08fe9f2-b108-4f8e-96b5-6387030a297c.JPG)

## GRANULARITY & CARDINALITY

It tells the level of how detailed your data is.

What is granularity in data warehouse?
What is Data Granularity? Data granularity is a measure of the level of detail in a data structure. In time-series data, for example, the granularity of measurement might be based on intervals of years, months, weeks, days, or hours.

- If data is performing good if stored hourly than the granularity level should be hour level.
- If data is performing good if stored daily than the granularity level should be day level.
- If data is performing good if stored weekly than the granularity level should be Week level.
- If data is performing good if stored monthly than the granularity level should be Month level.

![1](https://user-images.githubusercontent.com/33677647/204113420-01b00d4a-e5f3-4396-b879-607f802ed815.JPG)

Meta Data is data about data,
means if we have any data, where it is actually stored, whats its type, formate, etc.<br/>
we define where the source/ path of each data file is<br/>
as DWH is not real time database, so it has to updated manually each day, it will be difficult to check each time that from where we have to get the file of new data and what is the target path to load the file,
so meta data storess the location of each data file and the location of where it has to be loaded, so it save time in extracting and loading of data in DWH.

- meta table defines which table is source and which table is target<br/>
- and how to tranform the data (how ww have to convert source data into desired transformed data).

![1](https://user-images.githubusercontent.com/33677647/204114181-98c1f557-921a-4177-8686-7e3932a27047.JPG)

- Data coming from various source like any RDBMS , xml, flat file, .txt, .csv, .xml, etc.<br/>
- Now ELT will be performed on that data, Then It will go to staging area.
- Staging area is a temporary storage area, we use before complete transformation and load to DWH, this staging is present in tools like informatica or Talend.

![1](https://user-images.githubusercontent.com/33677647/204114304-f72a6cf7-da62-4fc1-a10b-0eba512972e4.JPG)

![1](https://user-images.githubusercontent.com/33677647/208683950-3eade0fa-99fd-470f-bb9d-d7770e5cf252.png)

## Data Migration
is a process of moving application data from old systems to new ones. It typically requires transferring data between Storage types or formats. Automated migration frees up human resources from tedious, error-prone tasks.

![2](https://user-images.githubusercontent.com/33677647/208684452-4f98753b-05b1-4e72-bc2a-318ec4c1b302.png)

## Data WareHousing

Data integration is often implemented in Data Warehouses through specialized software that host large data repositories from internal and external resources. Data is extracted, amalgamated, and presented in a unified form.

a **data mart** that stores combined data from marketing, sales, and operations. 

![1](https://user-images.githubusercontent.com/33677647/208685690-3375005d-b90f-413e-86c7-4d3474315c50.png)

## Data consolidation
Is usually associated with moving data from remote locations to a centralized location or combining data due to an acquisition or merger of two or more companies. In this example, two companies merge. Imagine the sales team in each company use different tools. The two sales teams, might crossover into each other's accounts, not realizing that a candidate is already a customer. The goal is to have a unified sales tool and single source of truth for the new unified company so that the sales teams don't get conflicting or overlapping data.

![3](https://user-images.githubusercontent.com/33677647/208685704-5c794a84-5b8d-49f0-a2de-ac9109920631.png)

## Data synchronization 
is a process of ensuring that two or more locations contain the same up-to-date data. Adding, changing, or deleting a file from one location will mirror the action at the new location. 

![1](https://user-images.githubusercontent.com/33677647/208687841-ba9d6627-6c84-48d7-9503-0bce59c17bf4.png)

 ## Change data capture
 
 Data Warehousing involves the extraction and transportation of data from one or more databases into a target system or systems for analysis. This involves the extraction and transportation of huge volumes of data and is very expensive in both resources and time. The ability to capture only the changed source data and to move it from a source to a target system in real-time is known as change data capture, often abbreviated CDC. Capturing changes reduces traffic across a network and thus helps reduce ETL time. The CDC feature introduced Intel and data integration simplifies the process of identifying the change data since the last extraction, CDC and talent quickly identifies and captures data that had been added to update it in or removed from the database tables and makes this change data available for future by applications are individuals

![2](https://user-images.githubusercontent.com/33677647/208687870-253e272b-6f33-4b12-96ec-6d9d49d5c112.png)

 data integration simplifies the process of identifying the change data since the last extraction, CDC and talent quickly identifies and captures data that had been added to update it in or removed from the database tables and makes this change data available for future by applications are individuals. 

![3](https://user-images.githubusercontent.com/33677647/208688585-5eb1e944-736e-4703-97d5-be1964c26816.png)

![0](https://user-images.githubusercontent.com/33677647/208690292-f6d0d864-e951-407c-9174-4bc25f0ef466.png)
![01](https://user-images.githubusercontent.com/33677647/208690395-d0030554-f1e1-433b-8eda-7dfc6a5496be.png)
![1](https://user-images.githubusercontent.com/33677647/208690323-6d7e43c7-6197-4977-b6f8-7a57658e1e14.png)
![2](https://user-images.githubusercontent.com/33677647/208690332-499bdb96-1963-4284-9a8a-17c52535e262.png)
![3](https://user-images.githubusercontent.com/33677647/208690429-10adbb9d-2375-418d-a207-07417fc13055.png)
![4](https://user-images.githubusercontent.com/33677647/208690452-b26fb6ac-42ad-438f-aa45-658d0716a071.png)

you can use data quality components in a data integration job to duplicate data. Here, the same customer appears in three sources with different spelling. The first step is to identify duplicates using data matching components. They give you plenty of options to fine-tune the duplicate detection and their survivorship rules. Data can then be repaired, improving the quality of data in the company,

![5](https://user-images.githubusercontent.com/33677647/208690624-53afc275-51c2-49f2-a53f-afd8cf693d29.png)

## Staging area

It is usually one day older than current data.

![0000](https://user-images.githubusercontent.com/33677647/209848505-2c11eb0b-bcdb-4a5b-a90f-d50cd3225188.png)

The Data Staging Area is a temporary storage area for data copied from Source Systems. In a Data Warehousing Architecture, a Data Staging Area is mostly necessary for time considerations. In other words, before data can be incorporated into the Data Warehouse, all essential data must be readily available.\

 it, produces integrated, cleaned data, and stages it for loading into data warehouses, data marts, or Operational Data Stores. A data staging tool is accessible, and the data is in a database.
 
 To keep the workload for the source system (where all the raw data is present/ operational system ) to a minimum. As if we put data directly to DWH and if we feel that we needed different data style then we will again put load on source, so intead we load data to Staging area, design it a/c to our need and the give it to DWH, so not to put load on Source Sys. again and again.

## ODS (operational data store)

![00](https://user-images.githubusercontent.com/33677647/209848495-2e373315-5ba3-48c2-afab-f2db23cdb282.png)
![1](https://user-images.githubusercontent.com/33677647/209848580-2bc32c87-6434-4579-8820-9fb9bb51e659.png)

## DIMENTIONAL MODELING

the design methdologies followed to build dataware house is called Dimensional modeling.<br/>
The end result of dementional modeling is we end up building a star schema or snowflacs schema.

![DM](https://user-images.githubusercontent.com/33677647/209848666-e8737c1d-05f9-46b7-9d4b-c3da793004a8.png)

![0000](https://user-images.githubusercontent.com/33677647/209849080-b167ea7a-e05d-448b-ac86-479466e3570e.png)

Above are the steps to build a dimensional model

## STAR SCHEMA

A star schema contains both, the dimension tables and the fact tables in it. Whereas A snowflake schema contains all, the three- dimension tables, the fact tables, and the sub-dimension tables. It is a top-down model type. It is a bottom-up model type.

![1](https://user-images.githubusercontent.com/33677647/209855091-25b84ae7-bbad-447a-a673-2daeddb71c57.png)
![6](https://user-images.githubusercontent.com/33677647/209850842-971c5232-eeaa-4d13-9c2b-9cf727449eb1.jpg)
![2](https://user-images.githubusercontent.com/33677647/209850889-ddd230a4-e039-4577-a92b-9657d9895fee.jpg)
![1](https://user-images.githubusercontent.com/33677647/209850862-08f84fe4-7fd1-429b-ace6-e0387db297cd.jpg)
![3](https://user-images.githubusercontent.com/33677647/209850903-b51fe65c-e627-4474-8d98-fbbc504c30be.png)
<img width="560" alt="5" src="https://user-images.githubusercontent.com/33677647/209850918-3e5ea128-1406-4ec5-9d1c-289965f8390b.png">
![2](https://user-images.githubusercontent.com/33677647/209855105-9d5a3831-3160-44a5-b1f2-0dfac3c79359.png)



## Granularity & cardinality

 In a data warehouse, data granularity is the level of detail in a model or decision making process.
 
 What is Data Granularity? Data granularity is a measure of the level of detail in a data structure. In time-series data, for example, the granularity of measurement might be based on intervals of years, months, weeks, days, or hours.
 
 - If data performs good if stored daily then granularity level should be Day level.
 - If data performs good if stored weekly then granularity level should be Week level.
 - similarly it also includes about how much data is needed for fact table.
 - The bigger the data the bigger the fact table the higher the granularity level.


## SCD (Slowly changing dimension)

What is a Slowly Changing Dimension? A Slowly Changing Dimension (SCD) is a dimension that stores and manages both current and historical data over time in a data warehouse. It is considered and implemented as one of the most critical ETL tasks in tracking the history of dimension records.<br/>

Soppose if the customer Ali lived at address A in 2022, then he moved to address B in 2023, So this kind of history preservation is called SCD.<br/>
There are 6 types of SCD but 3 are most common.

![1](https://user-images.githubusercontent.com/33677647/209855250-d469ad2a-168c-48f5-8f2c-0389d939cf6d.png)

What are the 3 types of SCD?
Introduction to Slowly Changing Dimensions (SCD)
Type 1 – This model involves overwriting the old current value with the new current value. ...
Type 2 – The current and the historical records are kept and maintained in the same file or table.
Type 3 – The current data and historical data are kept in the same record.

![1](https://user-images.githubusercontent.com/33677647/209855737-14edaea4-63a4-43d4-a387-35c9a4046ba4.png)
![2](https://user-images.githubusercontent.com/33677647/209855741-775c950f-4266-4ce4-aab2-46dd59ffc093.png)
![3](https://user-images.githubusercontent.com/33677647/209855747-1e3ad948-5da9-496e-8146-ade9b5426e76.png)

## Surrogate Key

What is the difference between surrogate key and primary key?
Image result for Surrogate key in DWH
It turns out a surrogate key is very similar to a primary key in that it is a unique value for an object in a table. However, rather than being derived from actual data present in the table, it is a field generated by the object itself.

Natural /Bussiness key --> primary key

How is surrogate key generated?
​ A surrogate key. It often takes the form of a hashed value of multiple columns that will create a uniqueness constraint for each row. is a primary key that, instead of existing in your underlying dataset, is derived in the analytics layer itself.

These surrogate keys are used to join dimension and fact tables.

- Usually, database sequences are used to generate surrogate key so it is always unique number
- Surrogate keys cannot be NULLs. Surrogate key are never populated with NULL values.
- It does not hold any meaning in data warehouse, often called meaningless numbers.
- It is just sequentially generated INTEGER number for better lookup and faster joins.

Why surrogate keys are used in Data warehouse?
Basically, surrogate key is an artificial key that is used as a substitute for natural key (NK) defined in data warehouse tables. We can use natural key or business keys as a primary key for tables. 

- Advantages of Surrogate Key
Below are some of advantages of using surrogate keys in data warehouse:

- With help of surrogate keys, you can integrate heterogeneous data sources to data warehouse if they don’t have natural or business keys.
- Joining tables (fact and dimensions) using surrogate key is faster hence better performance
- Surrogate keys are very helpful for ETL transformations.
- Data warehouse Surrogate keys are usually small integer numbers that makes smaller index and better performance
- Surrogate keys are required if you are implementing slowly changing dimension (SCD)

1

- (Real story) Once a bank used to make reports, but they had no dataware house, so they used to get data for it from their transactional system (OLTP), so due to load on transactional system, it crashed and blocked all its ATMs ( the end).
- DWH is used for reporting. Collects data from differenrt departments and centralize it (avoiding duplications coming from diffeneret departments, coming same data)
 for reportung
## Steps to be considered when building or enhancing a dataware house or you want to add a new department :

2

- we use star schema dimentional model because we want the ETL to be as easy as possible, we perform queries ans SSAS easily.

## Scenario -- A company named bluster block which retals to VFS movies--- we'll use star schema for the purpose.

** STEP_1 : IDENTIFY BUSSINESS PROCESS :

Decide what bussiness process we want to model :

1_ **IMPACT** : We have to consider the impact of creating this dataware house on BI department, how its going to help them on daily bases
2_ **Risk** : The risk associated with building a DWH is that how we going to get the data? is it going to be very difficult? will the model be very complex? will data be very dirty?

4

- Now we have to identify the grain of the fact table.
- The most important decision to design a fact table is to identify, what is its grain.
- It is the center of our star schema.
- Facts are the measurement of success or failure in bussiness
- A table that contains all the facts about the bussiness, how successful it is, how many sales do we have ? etc

We must keep fact table to grain level, means if we have employee_id, employee_salary in a fact table, the ww should keep data to grain level means do not put average salaray of customer as a column so that when someone comes and as the monthly salary of employye then you cannot de-aggregate it, so keep it to grain level.
As we cant predict, what queries users are going to run so we just keep our table at grain level (no aggregated  data, raw values).
So that they can query any thing they want.

Plus!!!

If you design your DWH fact table at monthly level, then later on you want it to be on daily level, it will not be possible because their will be no past data on daily level, and even if its possible, then we will have to reset all our dimensions as well.
So that they can query any thing they want.

As we cant predict, what queries users are going to run so we just keep our table at grain level (daily data).


5,6,7,8

Dimentional tables are the descriotion of fact table

9

# Staging area

it is a area where data is fetch and put from source application. first we get the data from source app and put here (LAnding zone), then we transform the data and put in final table of edw that is accessible by all other BI developers.

is this is the 'E' area for ETL.

in DWH we donot fetch the source data and directly put in final EDW table . intead we take the data put it in staging area, then do transformation and the put it in final EDW table that is accessible by BI dev.

![Untitled](https://github.com/sundas586/Data_Warehousing/assets/33677647/a47b93e4-bc4a-42f8-b7d6-c030f6360fad)
![staging-area](https://github.com/sundas586/Data_Warehousing/assets/33677647/a08631f7-6184-4734-9fe3-3d1841e862d6)

# Persistent vs non-persistent staging layer :

There are two types of staging layer:

- Non-persistant staging layer : is the layer that takes data from source the put it in EDW , after putting data in EDW, it trubcates all the data from stage layer, each time aftert lading and inserting the data from source to EDW (stage = Truncate/ Insert)

- persistent staging layer : it is the stage layer that is not truncate insert, it keeps all the data of history (stage : default/ insert)




