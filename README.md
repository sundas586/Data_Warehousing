# Data_Warehousing

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

![6](https://user-images.githubusercontent.com/33677647/209850842-971c5232-eeaa-4d13-9c2b-9cf727449eb1.jpg)
![2](https://user-images.githubusercontent.com/33677647/209850889-ddd230a4-e039-4577-a92b-9657d9895fee.jpg)
![1](https://user-images.githubusercontent.com/33677647/209850862-08f84fe4-7fd1-429b-ace6-e0387db297cd.jpg)
![3](https://user-images.githubusercontent.com/33677647/209850903-b51fe65c-e627-4474-8d98-fbbc504c30be.png)
<img width="560" alt="5" src="https://user-images.githubusercontent.com/33677647/209850918-3e5ea128-1406-4ec5-9d1c-289965f8390b.png">

