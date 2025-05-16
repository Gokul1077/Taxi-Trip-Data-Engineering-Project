#  Microsoft Fabric data project using New York City taxi data.
![image](https://github.com/user-attachments/assets/e2db5557-70d5-4822-8986-880c2e1b7559)

**Source:**
Dataset Link: https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page

**Project Workspace:** 
![image](https://github.com/user-attachments/assets/57269328-fd80-4a18-a002-5a44268f262e)

**Data factory section :** (ETL Pipelines)
![image](https://github.com/user-attachments/assets/4673bca4-7df1-4549-8302-96f99e9f907b)
**Staging Data preparation:** 
1.	“pl_stage_taxi_lookup_zone” pipeline contains a Copy activity: to get the data from Lakehouse (in csv) and load into warehouse (DB).
2.	“pl_stg_taxi_data_process” pipeline contains Copy activity and Stored Procedure: to get the data from Lakehouse (in parquet) and load into the data-warehouse (DB). Here, a Stored Procedure is used to track pipeline and taxi trip data metadata.
![image](https://github.com/user-attachments/assets/1b227058-fa62-4208-b01b-27ead9f4de8a)

**Presentation / Gold Layer data Preparation:**

3.	"pl_stg_to_DTM" pipeline contains Dataflow activity and stored Procedure:
![image](https://github.com/user-attachments/assets/853953fb-9ba9-4f9b-8271-e208ae96ef51)
4. The above-mentioned Dataflow activity workflow:
![image](https://github.com/user-attachments/assets/62b2a51d-f622-4b4b-b01b-e13c89821fe6)
   
**Orchestration Data Pipeline:**

5. Created a separate pipeline to invoke the source_to_stg pipeline and stg_to_dtm pipeline:
![image](https://github.com/user-attachments/assets/5ad88ace-3962-4372-a9d8-8faa69c45de8)

**Stored Procedure Part:**

Data Clean Procedure:

![image](https://github.com/user-attachments/assets/878d59e6-a1ba-4962-8cc9-fb643853e2c9)

Metadata Processing Log:

![image](https://github.com/user-attachments/assets/8f4e18aa-5720-470b-8b6a-dd20a79c7ef5)



**Datawarehouse:**

**Meta-data Table:**
![image](https://github.com/user-attachments/assets/838c93e1-9169-46a6-bee1-9e120726f6c9)

**Stage Table:**
![image](https://github.com/user-attachments/assets/18754750-35b3-41de-b048-725baa152cd2)

**Presentaion / DTM Table:**
![image](https://github.com/user-attachments/assets/0865fdaf-22ab-453b-986c-f8623ee5d791)


**Dashboard:**
      ![image](https://github.com/user-attachments/assets/6ff220fe-c9cd-45e6-9682-4d15f5370b15)



Project Outcome:
Learned how to create an orchestration pipeline in Microsoft Fabric to automate the staging and presentation layers of data pipeline.
