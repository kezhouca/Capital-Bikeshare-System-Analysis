### The real-time station infomation and the station status data are refreshed every 10 seconds:  
https://gbfs.capitalbikeshare.com/gbfs/en/station_information.json  
https://gbfs.capitalbikeshare.com/gbfs/en/station_status.json  
  
### We can get the data from the above urls every 10 seconds by [station.ipynb](station.ipynb)  .
### The station info and status data are extracted from the json format files and saved on the cluster:  
```
/user/chowkec/capitalbikeshare/data/stationinfo/station_info.csv
/user/chowkec/capitalbikeshare/data/stationstatus/station_status.csv

```
### The combined station status data is processed by spark and saved here:
```
/user/chowkec/capitalbikeshare/output/stationstatus
```