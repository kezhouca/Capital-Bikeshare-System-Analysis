# 0. Data source
Our dataset is from: https://www.capitalbikeshare.com/system-data  
copy the links in https://s3.amazonaws.com/capitalbikeshare-data/index.html to the [data_urls.txt](data_urls.txt) file.
# 1. Download trip data
```
git clone https://csil-git1.cs.surrey.sfu.ca/big-data-squad/capital-bikeshare-system-analysis.git
cd capital-bikeshare-system-analysis/data_processing
mkdir data  
cd data  
```
Download data using the links in data_urls.txt:  
```wget -i ../data_processing/data_urls.txt```  
Since the data is all in .zip format, and there is no direct Spark solution to read in .zip, we need to convert to .gz format  
First unzip all files in .zip format to csv:  
```unzip "*.zip"```  
Now that we have all csv files, remove all *.zip files  
```rm *.zip``` 
Fix two file names  
```
mv 201907-capitalbikeshare-tripdata 201907-capitalbikeshare-tripdata.csv 
mv 201908-capitalbikeshare-tripdata 201908-capitalbikeshare-tripdata.csv
```
```gzip *.csv```  
Remove all csv files  
```rm *.csv```  

# 2. Upload data to cluster
```
hdfs dfs -mkdir capitalbikeshare
hdfs dfs -mkdir capitalbikeshare/data
hdfs dfs -mkdir capitalbikeshare/data/trip
hdfs dfs -mkdir capitalbikeshare/output
hdfs dfs -copyFromLocal *.gz capitalbikeshare/data/trip
```
# 3. Share data 
```
hdfs dfs -setrep -R 1 capitalbikeshare/
hdfs dfs -chmod 0771 /user/chowkec
hdfs dfs -chmod -R 0775 /user/chowkec/capitalbikeshare/
```
We can visit our data on hadoop cluster by:
```
/user/chowkec/capitalbikeshare/data/trip
```

