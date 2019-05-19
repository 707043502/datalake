# ETL For Sparkify V3.0.0

## 1.INTRODUCTION

🏡Sparkify has been collecting on songs and user activity on their new music streaming. 🙏In order to support further data analysis which is really important for such online bussiness, we launched 👨‍👦`ETL For Sparkify v1.0.2`. However with the growth of our market😁, it becomes hard🤣 to maintain the ETL process on a single node any more, and we are urged to move this service to AWS., Which in turn leads to project of 👨‍👨‍👦‍👦 `ETL For Sparkify v2.0.0`. In order to add more flexibility to our analysis tasks🎛, we launch our new data lake project `ETL For Sparkify v3.0.0`. 

## 2.DATA ORGANIZATION
Data lake brings great flexibility for analysis team to customize there data without compromsing to the database schema. This change is hope to lead to further bussiness success.


**THINGS UNCHANGED:**
We keep using the star schema as it brings convinience to our data analysis team👌
Tables are organized as:
- FACTS: songplays
- DIMENSION: users, songs, artists, time


The following picture shows how we organize our tables.
![image](https://r766469c826419xjupyterlr5tapor7.udacity-student-workspaces.com/files/schema.png)


**DECISIONS WE MAKE:** 
We precaculated some tables for business team using spark, however bussiness teams are free to create their owns from the data stored in S3🍺.



## 3.PRACTICE
Users can run the scripts follow steps bellow😋

`Step0`: **configure your Spark env**
- a lot of things to do.

`Step1`: **data preparation**
- Copy data from S3 storage below and store them to our staging table
    - Song data: ` s3://udacity-dend/song_data` to table `staing songs`
    - Log data: `s3://udacity-dend/log_data` to table `staging events`

`Step2`: **start ETL**
- using<br> &emsp;&emsp;```python etl.py```
    
## 4.FILEs 
In case any customization,we post out our file organization strategies for referencing.👨

```create_tables.py```: process to prepare database

```sql_helper.py```: basic codes used in this project, including:💀
- configure original schema for staging talbes
- build dataframe from staging tables

```etl.py```: main logic that maintain the ETL process

- run codes to build tempTable
- save table to certain path

```dwh.cfg```: config files provides configuration of cloud environment


