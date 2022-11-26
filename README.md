# Data_Warehousing

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
- Data warehouses only accept structured data from multiple sources.
- Databases perform best when there's a single source of structured data and have limitations at scale.
- 
![1](https://user-images.githubusercontent.com/33677647/204098919-abfaeaed-1c12-4ee7-82b0-a79ccd702434.JPG)

End User --> BI analysts <br/>
We do not add each and every real time data (e.g transactions) to dataware house. because we dont want our anaalysis to be affected.

## ETL

The process of extraction of operational data into your DWH is called **ETL**

**What is operational database system?**<br/>
operational database systems are oriented toward real-time, transactional operations.**

- Operational data is extracted,transformed and loaded to DWH.
- then it can be used by End Users for visualiztion with help of **OLAP (Online Analytical processing).**
- Later visualiztion can be done using PowerBI, Tablue, etc.
- 
- 





