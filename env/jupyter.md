# 1. Run jupyter notebook in your terminal, or put the below into .bashrc:
```
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export HADOOP_HOME=/usr/shared/CMPT/big-data/hadoop-2.6.0
export SPARK_HOME=/usr/shared/CMPT/big-data/spark-2.4.4-bin-hadoop2.7
export PYSPARK_PYTHON=python3
export PATH=${SPARK_HOME}/bin:$PATH

export PYSPARK_DRIVER_PYTHON=jupyter
export PYSPARK_DRIVER_PYTHON_OPTS='notebook'
```
Then run:
```pyspark```
The Jupyter Notebook page will show in your browser.

# 2. Run jupyter notebook on gateway,  pick a port number 8xxx you like:
Add to .ssh/config locally:
```
  LocalForward 8349 localhost:8349
```
run on cluster:

```
module load spark
PYSPARK_DRIVER_PYTHON=jupyter-notebook PYSPARK_DRIVER_PYTHON_OPTS="--no-browser --port=8349" pyspark
```
