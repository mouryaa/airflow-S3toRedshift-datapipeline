# Data Pipelines with Airflow

The source data resides in S3 and needs to be processed into a data warehouse in Amazon Redshift. The source datasets consist of CSV logs that tell about user activity in the application and JSON metadata about the songs the users listen to.

## Project Setup - to run locally

1. Install Airflow, create variable AIRFLOW_HOME and AIRFLOW_CONFIG with the appropiate paths, and place dags and plugins on airflor_home directory.
2. Initialize Airflow data base with `airflow initdb`, and open webserver with `airflow webserver`
3. Access the server `http://localhost:8080` and create:

**AWS Connection**
Conn Id: Enter aws_credentials.
Conn Type: Enter Amazon Web Services.
Login: Enter your Access key ID from the IAM User credentials you downloaded earlier.
Password: Enter your Secret access key from the IAM User credentials you downloaded earlier.

**Redshift Connection**
Conn Id: Enter redshift.
Conn Type: Enter Postgres.
Host: Enter the endpoint of your Redshift cluster, excluding the port at the end.
Schema: This is the Redshift database you want to connect to.
Login: Enter awsuser.
Password: Enter the password created when launching the Redshift cluster.
Port: Enter 5439.

## Data Source
* Log data: `s3://sparkify-data-mourya/log_data`
* Song data: `s3://sparkify-data-mourya/song_data`
