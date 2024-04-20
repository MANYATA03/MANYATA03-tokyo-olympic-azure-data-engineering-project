# tokyo-olympic-azure-data-engineering-project
tokyo-olympic-azure-data-engineering-project
*step- two 
data storage in azure --containers ,file shares ,queues and tables
click on left side container---then clck +containers
name the container-tokyoolympicdata-contair created


3)inside container--add directory 
of raw and transformed data--we will get our data we will ingest our data from source using adf after using databrick we will transform the data and lod to transformed data .


4)now use adf--concole->data factories in new tab
-->create data factory--use resource u already have --tokyo-olympic-df as instance name--next --create --deployment is completed --go to resources--new pannel for data factory---launch studio

5)launch studio--author-pipeline -name as--data-ingestion
copy data from data source /api to our storage ----in activities drag and drop copy data

6)link our source to data factory--gitub data -have raw link and go to source
+new then search http because we r getting our data from http -continue-specify csv as format -give logical name 
create link sevice from source to github
add new 0-->then add base url-->
raw of github
Authentication type-anonymous
First row as header
Import schema ->None
ok->u can previw data 

7)load data to azure data lake storage ---click sink-new-azure datalake gen2--if u want to convert data into any other form u can do but we will stick to this only.
csv

CONTINUE--ADD STORAGE NAME WHICH IS OUR STORAGE ACCOUNT
Select path --browse-add raw data--validate and debug for errors


do this for all other fies


**********jump to azure data bricks 
console-->azure databricks-->create azure databricks-->deployement in process
like previous -->
launch workspace--to databricks-->create compute-->Access mode
--single node-->wait upto lclustor is formed



**transform data using notebook +new ->notebook 
form a connection between azure databricks to azure data storage 

attach clustor in connetion option

for connection go to console-->app registrations -->new-->app

Application (client) ID
:
5da8287f-53c9-422f-befc-d647601a5bcb

Directory (tenant) ID
:
132343a2-0c0b-4e7a-b414-0b837984a8f3

take these two id for creating connections 

click on certificates and secrets -->Add a client secret
-->secret key

secret key -value-gWG8Q~SRDDRvJKv_ik8pHkiXd3dZjcMcNbX0bdvn

modify by filling keys
you can use key vaults to store secret key as putting key in code is not best practise always use key vault

****generally when we write the spark code we create spark session and craete app and the  write  code but on data bricks all things are already assigned
just write spark-->
SparkSession 
- hive

SparkContext

Spark UI

Version
v3.4.1
Master
local[*, 4]
AppName
Databricks Shell

-------------------------









