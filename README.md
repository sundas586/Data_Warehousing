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








