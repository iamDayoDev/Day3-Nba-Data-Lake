# DevOps Challenge - Day 3: NBA Data-Lake

![Data_lake D3](https://github.com/user-attachments/assets/2bd9faf3-8513-49ea-9628-1db225a8fd83)

## Project Overview:

This project sets up an NBA data lake on AWS, enabling data storage, processing, and querying. 

## Prerequisites

- Sportsdata.io API Keys
- AWS Account
- IAM Role/Permissions: Ensure the user or role running the script has the following permissions

## Key components include:

1. Amazon S3: Stores raw and processed NBA data in JSON format.
2. AWS Glue: Creates a database and external table for schema definition and data cataloging.
3. Amazon Athena: Configures query capabilities for the data stored in S3.

## STEPS TO FOLLOW:

## Step 1: Open CloudShell Console

1. Go to aws.amazon.com & sign into your account

2. In the top, next to the search bar you will see a square with a >_ inside, click this to open the CloudShell

## Step 2: Create .env file

1. In the CLI (Command Line Interface), type
```bash
nano .env
```
2. paste the following line of code into your file, ensure you swap out with your API key
```bash
SPORTS_DATA_API_KEY=your_sportsdata_api_key
NBA_ENDPOINT=https://api.sportsdata.io/v3/nba/scores/json/Players
```

## Step 3: Create the nba_data_lake.py file
1. In the CLI (Command Line Interface), type
```bash
nano nba_data_lake.py
```


2. Copy the `nba_data_lake.py` python script from this repo: `https://github.com/iamDayoDev/Day3-Nba-Data-Lake`

-Go back to the Cloudshell window and paste it in the `nano nba_data_lake.py` window.


3. Press ^X to exit, press Y to save the file, press enter to confirm the file name

## Optional Step: Install python-dotenv
If you dont have a dotenv package installed, you will have to run this command in your terminal to install the package:

```bash
pip install python-dotenv
```

## Step 4: Run the script
1. In the CLI type
```bash
python nba_data_lake.py
```
-You should see the resources were successfully created, the sample data was uploaded successfully and the Data Lake Setup Completed

## Step 5: Manually Check For The Resources on the AWS console

4. Head over to Amazon Athena and you could paste the following sample query:
```bash
SELECT FirstName, LastName, Position, Team
FROM nba_players
WHERE Position = 'PG';
```

-Click Run
-You should see an output if you scroll down under "Query Results"

## Step 6: Run this script to delete your resoucres automatically.
1. In the CLI type
```bash
nano delete.py
```

2. Copy the `delete.py` python script from this repo: `https://github.com/iamDayoDev/Day3-Nba-Data-Lake`

-Go back to the Cloudshell window and paste it in the `nano delete.py` window.

3. Press ^X to exit, press Y to save the file, press enter to confirm the file name 

-All your resources will be Deleted. 


### You have successfully created an NBA Data Lake which stores and query data using Amazon S3, Glue and AWS Athena.
