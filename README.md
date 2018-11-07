# How to Hue Dashboards
This repository will walk through a tutorial on how to access, and use Hue dashboards.
### 1. Open Hue with username and password "cloudera" in your cloudera quickstart VM.
- If you do not have a VM setup follow steps from:
  https://community.cloudera.com/t5/Hadoop-101-Training-Quickstart/How-to-setup-Cloudera-Quickstart-Virtual-Machine/ta-p/35056
### 2. Go to  and download the .csv file. 
- The rest of the example will use https://www.kaggle.com/lava18/google-play-store-apps
- (This file can be any indexable file.)

### 3. Extract the file from the zipped folder and move it to HDFS.
- Use the command: `sudo -u hdfs hadoop fs -put {file location} {hdfs location}`
- If you have permission issues with the file use the command: `chmod +rwd {file}`

### 4. Create an index for a Dashboard
- Go to the drop-down box under the "Query" button and select "Dashboards"

    ![alt text](https://github.com/samgedwillo/How-To-Hue-Dashboards/blob/master/Dashboard.PNG "To Dashboard")
- Follow the link to create an index.
- Pick the data file from the location where you -put in HDFS.
- Confirm the dataset is split appropriately.
- Move it to a table. (follow the "Next" button's instructions.)