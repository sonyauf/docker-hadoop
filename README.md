[![Gitter chat](https://badges.gitter.im/gitterHQ/gitter.png)](https://gitter.im/big-data-europe/Lobby)

# ID2221 Project

Docker images for HDFS storage and pyspark-jupyter
Forked from big-data-europe/docker-hadoop git 

## Setup

To deploy docker containers, run:
```
  sudo docker-compose up
```

Copy the data to namenode
```
  sudo docker cp data namenode:/tmp/
```

Connect to namenode bash
```
  sudo docker exec -it namenode /bin/bash
```

 and put into HDFS
```
  hdfs dfs -mkdir -p /user/root
  hdfs dfs -put tmp/data user/root/
```

To start Jupyter notebook find the token
```
  sudo docker exec pysparkjupyter jupyter server list
```

and copy it to http://127.0.0.1:8888/?token=

## The code

pysparkjupyter/Twitter_model_training.ipynb processes data stored in HDFS and trains a Logistic Regression model on it.

pysparkjupyter/Twitter_data_processing.ipynb streams data from HDFS data_stream folder and visualizes results in a pie chart.