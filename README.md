# How to Hue Dashboards
This repository will walk through a tutorial on how to access and utilize Hue dashboards.

### Prereqs
1. Cloudera Quickstart
2. Hue, Hadoop, Hive, and Solr are running
3. A dataset (provided)

### Dataset
https://www.kaggle.com/census/total-construction-spending-data-collection 

### 1. Open Hue with username and password "cloudera" in your cloudera quickstart VM.
- Your VM should already have Hue bookmarked in its default browser.
- If you do not have a VM setup follow steps from:
  https://community.cloudera.com/t5/Hadoop-101-Training-Quickstart/How-to-setup-Cloudera-Quickstart-Virtual-Machine/ta-p/35056

### 2. Extract the file from the zipped folder and move it to HDFS.
- unzip file: 'unzip filename'
- Use the command: `hadoop fs -put fileLocation /user/hive/warehouse/`
  Alternatively, if you placed your file elsewhere `sudo -u hdfs hadoop fs -put {file location} {hdfs location}`
- If you have permission issues with the file use the command: `chmod +rwd {file}`

### 3. Move the dataset into Hue.
- Go to table
- Click the +
- Use the file browser to select your dataset
- Follow the dialogue 

### 4. Index the Data with Solr
- Go to quickstart.cloudera:8888/indexer/collections
- Click the "Create" button. Name the new index and again locate for the data file is in HDFS.
- Add desired indexes and IDs to separate your data.

### 5. Create a new Dashboard.
- After you create your index. Go back to the original Hue select "Dashboards"

    ![alt text](https://github.com/samgedwillo/How-To-Hue-Dashboards/blob/master/Dashboard.PNG "To Dashboard")
- Choose the index you created.
- Fill the dashboard with various charts that will convey your data appropriately and help tell a story.
  (Remember, the data may not make sense to everyone, so be strategic with your dashboard to make it easy
   to read.)

### Problems
1. Incorrect permissions to load in dataset
    Fix: make sure the dataset is in the /user/hive/warehouse folder in hadoop. Hue doesn't have the correct permissions to access all folders. It does for this folder.

2. Always backtrack.
   If you load a dataset in hue and delete that dataset it will attempt to open at that same location and throw errors. Same for indexing. If you load in a dataset and then index, delete the index BEFORE deleting the data.

3. NameNode in Safemode.
   Sometimes namenode does not leave safemode(basically read only) after 
   startup is complete. 
   Fix: 'sudo -u hdfs hadoop dfsadmin -safemode leave'
   This script is deprecated but still runs




### Sources
https://www.kaggle.com/census/total-construction-spending-data-collection
https://www.tutorialspoint.com/apache_solr/apache_solr_indexing_data.htm
https://www.youtube.com/watch?v=Gi1iOZmNzqE

#### Contact
Sam Gedwillo (samgedwillo@gmail.com)
