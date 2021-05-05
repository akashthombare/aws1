# aws1
Error Scenario
5. Mule Responsbile for Transaction Mangement:
a. Input csv file with 100 records in AWS S3 Bucket i.e Source System . IT has 3 sub folder Done , Error and Main
b. Mule batch jobs reads S3 bucket as schedule every 1 hour
c. Once it reads file , it moves it to Done folder and rename the file wiht time Stamp
d. Same batch job once read will call Rest Service (same as in 3) and publish 10 records.
e. Create error  condition e.g Provider service not avialble after 6th transaction .
f. Write the remaining 40 records in some temperory directory.

6. Source Responsible for Transaction Management:
a. Input csv file with 100 records in AWS S3 Bucket i.e Source System . IT has 3 sub folder Done , Error and Main
b. Mule batch jobs reads S3 bucket as schedule every 1 hour
c. Once it reads file , it moves it to Done folder and rename the file wiht time Stamp
d. Same batch job once read will call Rest Service (same as in 3) and publish 100 records.
e. Create error considtion e.g Provider service not avialble after 6th transaction .
f. Write the remainign 40 records in Error folder on AWs and 60 records in Done folder in AWS.

7.Data validation while reading the file.
a. Input csv file with 100 records in AWS S3 Bucket i.e Source System . IT has 3 sub folder Done , Error and Main
b. Mule batch jobs reads S3 bucket as schedule every 1 hour
c. while reading the soruce file ,  Valdiate the order amout filed , if its more then zero then only send to target else send record in effor file and write in local directory.
d. Same batch job once read will call Rest Service (same as in 3) and publish 10 records at a time.
e. Move the file in AWS in DONE Folder

8. Splitting the file based on data in the file
a. Input csv file with 100 records in AWS S3 Bucket i.e Source System . IT has 3 sub folder Done , Error and Main
b. Mule batch jobs reads S3 bucket as schedule every 1 hour
c. Read the soruce file , group by CustomerID , Send all order to the rest service for an cusotmer .
d. Rest Service (same as in 3) to get records by customer so can be any number of hits and not 10
e. Move the file in AWS in DONE Folder

9. WaterMarking Scenario which reading the data from DB in batch mode
