# data-analyst-charles
# Descriptive analysis 
# Project Description: Data of licensed rental properties with 5 or more units that have current (unresolved) issues by law
# Project Title: Rental standards-current issues
# Objective: This dataset contains data of licensed rental properties with 5 or more units that have current (unresolved)issues by law, The information in the rental guidelines database comes from several places. Certain data may not be up-to-date because of problems with synchronizing the data or the quality of the data in any of the sources.
# Source of dataset: My dataset comes from the Open Data Portal of the City of Vancouver website. It is in a file that AWS can read, which is.csv, and it is from a number of city sources.
Step 1:
 Bringing in data in this step, i will upload my CSV dataset from the source and store it in my newly made AWS S3 bucket so that it can be used and analyzed in the future. Because it is cheap, robust, and scalable, S3 bucket was chosen as my cloud storage on the AWS interface.
Creating my process for bringing in data making a plan for how I want the Data Ingestion process to work was the first step for me. This is a plan for what I want to do with the City of Vancouver website, my AWS interface, and the S3 bucket, which is the cloud storage tool i want to use. This was made with the draw.io file
# ![image](https://github.com/user-attachments/assets/23e2818c-c01d-4f2a-969b-2180ba1457fd)
# The process of creating my S3 Bucket on the AWS Platform:
• I went to my AWS Management Console; 
• I searched for "S3 bucket" and clicked "Create bucket";
• I gave my bucket a unique name that spelled out "Rent-standards-raw-charles"; 
• I clicked "Create Bucket" to finish making the bucket. 
Uploading/Ingesting my CSV File: 
• I went to my newly made S3 bucket and opened it; 
• I clicked "upload;"
• I then imported my CSV dataset by adding the downloaded file from my computer to my S3 bucket; 
· I was able to upload successfully from the snapshot below
# ![image](https://github.com/user-attachments/assets/efbe9841-666d-43b2-ad1e-87d56e9768ca)
# Step 2: 
Data profiling
 The process of profiling my dataset means looking at the problems, content, structure, and quality of it to make sure it is good enough to be cleaned. In other words, I will carefully look over my dataset in this step to see how good it is right now. This is a data preparation tool that helps me learn more about the quality of my dataset and how ready it is to be cleaned. I am going to use the AWS Glue DataBrew for this because it can store technical and business information that is ready to be cleaned. 
Data profiling process:
This shows the change from the stage of Data Ingestion to the stage of Data Profiling. This is a plan for how I want the data to get from an unstructured CSV file that I put into S3 to the AWS Glue DataBrew project and dataset creation that is shown here. I also used the draw.io app to make this. 
# ![image](https://github.com/user-attachments/assets/a4797074-cc42-4133-a541-20faa9e9ad01)

# •	
Some of the steps I took to profile my data on S3 and AWS Glue DataBrew 
How do I: on my AWS Console 
Making a "trf" bucket on AWS S3 
I made a bucket called " rent-standards-trf-cha" to store the profiled dataset results. I then went back to AWS Glue DataBrew to do the profiling. Profiling on AWS Glue DataBrew 
For the AWS Glue DataBrew service, I searched for it in my AWS Console. I then clicked on projects in the right-hand navigation bar and chose "Create Project." 
•Named the project " rent-stand-prj-cha" and chose "New dataset." 
•I gave the dataset "LabRole" permission and named it " rent-stand-ds-cha" 
 Finally, I clicked "create project" I then chose the "current-issues.csv"
dataset and "CSV" as the format. and waited for it to set up a lot of computing resources for me to do my data profiling. 
• The dataset didn't have a profile yet, so I created one to do data profiling. 
• I then made a job to see the results and made sure they would be saved in the "trf" bucket before running the job.
# ![image](https://github.com/user-attachments/assets/ac60f689-aa7d-47e1-9ab5-a7406b08c902)
# ![image](https://github.com/user-attachments/assets/b81b60b2-9594-4955-a53f-00e1913fff17)
# Data Quality Issues Identified during Data profiling Process:
a)	The dataset is all in one column and separated by a semicolon (;)  despite the fact that there are 475 rows. Consequently, I must divide the dataset into distinct columns in order to perform cataloguing and summarization.
b)	Invalid Values: "Multiple Classification" is not a group in its own right, and "position title" is not a specific position as a column heading.
#    Step 3: Data Cleaning
	The aim of data cleaning is to address the challenges observed in the data profiling stage. The data cleaning step is very important because it will increase the quality, and this will be done by using the AWS Glue DataBrew. Each cleaning step will also be documented with screenshots. The result will be a cleaned dataset. As we can see from the screenshot below.
# ![image](https://github.com/user-attachments/assets/87052fdd-14dd-469e-98d5-d10a4be20fe0)
# ![image](https://github.com/user-attachments/assets/3acc304b-beca-49ca-94a5-d87c160bea01)
# Data issues identified during my cleaning Process:
In my dataset, there were a lot of columns, which i dropped because I felt they where irrelevant There were also a few empty cells in the "URL" column, which i also dropped.
# Step 4: Data Cataloging
	Data Cataloging simply means the database used in the process of organizing cleaned dataset for analysis. I will use the AWS Glue Data Catalog tool to structure my data, because it is a metadata source or repository since it makes it easier to better understand, discover and use the datasets. Generally, Data Cataloging will help me in the creation of a central inventory for my data assets. It is important because it makes it easier to manage data for collaboration for conversion of semi-structured data to a structured data in the form of collection of tables. The AWS Glue is a very useful service for data Analysis tasks.
# ![image](https://github.com/user-attachments/assets/0cd0760c-8042-4454-8bdb-54fa5d69c056)
# Step 5: Data Summarization
	The goal of Data Summarization is to present my data findings in a concise and clear way. I will create the summarization by using the Extraction, Transform and Load (ETL) pipeline, because it contains three (3) phases from the AWS Glue. Summarized dataset also helps me generate insights from the dashboard by:
•	Extracting: Taking out database from the data catalog source
•	Transforming: Means summarization, and
•	Loading: Means transferring it or Loading the summarized data into a new pipeline (the curated bucket/zone)
# ![image](https://github.com/user-attachments/assets/a4f1c5e4-e4a4-4a1f-9542-45a1588a5bc9)
# ![image](https://github.com/user-attachments/assets/44c016ae-6b5e-4237-afe0-156cb653bec1)
# ![image](https://github.com/user-attachments/assets/d86d6d2e-5344-4987-8dd6-3f90bac90ab7)




