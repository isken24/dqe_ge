Project Description
Greate Expectations is a Python library that provides a framework for describing the acceptable state of data and then validating that the data meets those criteria.

Installation
	pip install great_expectations

Connection to database:
I used Snowflake database in my project. Connection should be established using following parameters:
	host = "****"  # The account name (include region -- ex 'ABCD.us-east-1')
	username = "****"
	database = "****"  # The database name
	schema_name = "****"  # The schema name
	warehouse = "****"  # The warehouse name
	role = "****"  # The role name
	table_name = "****"  # A table that you would like to add initially as a Data Asset
	password = "****"

For MSSQL databases connection string should follow given pattern:
	"mssql+pyodbc://<USERNAME>:<PASSWORD>@<HOST>:<PORT>/<DATABASE>?driver=<DRIVER>&charset=utf&autocommit=true"	


Usage:
Navigate to your workking directory.

Initialize your directory as a Great Expectations project by running the following command:
	great_expectations init

Configure a Datasource by calling command given below and follow instuctions:
	great_expectations datasource new

Create an Expectation Suite, which is a set of Expectations that are grouped together:

	great_expectations suite new


Explore DataDocs in "gx\uncommitted\data_docs\"


Create Checkpoints:

great_expectations checkpoint new <your_check_name>


After creation of checpoint I've modified Data in DB. 
"Class" column was dropped and some of the records in "daystomanufacture" were modified in order to fail tests. 

Results of second run of expectation suite can be found at 
"\gx\uncommitted\data_docs\local_site\validations\3\20231123-161519-my-run-name-template\20231123T161519.215274Z"