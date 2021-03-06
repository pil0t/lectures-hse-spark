# Масштабируемое машинное обучение и анализ больших данных с Apache Spark

### Образ с предустановленным Apache Spark
* Образ [Virtual Box](https://www.virtualbox.org/wiki/Downloads) доступен для скачивания по [ссылке](https://goo.gl/PrNTSJ)
* Пароль для входа в систему: 123

### Инструкция по установке Apache Spark
1. Для работы с Apache Spark необходимо наличие следующих пакетов 
  * Java SE Development Kit [https://www.java.com](https://www.java.com)
  * Scala Build Tool [http://www.scala-sbt.org](http://www.scala-sbt.org/)
  * Python 2.7 [https://www.python.org](https://www.python.org/download/releases/2.7/)
  * Jupiter Notebook [http://jupyter.org](http://jupyter.org/install.html)
2. Скачать дистрибутив Apache Spark с [официального сайта](http://spark.apache.org/downloads.html)
3. Распаковать скаченный дистрибутив в директорию /opt/spark-2.1.0-bin-hadoop2.7
4. В файл ~/.bashrc добавить следующие строки
```bash
export SPARK_HOME=/opt/spark-2.1.0-bin-hadoop2.7
export PYTHONPATH=$SPARK_HOME/python:$SPARK_HOME/python/build:$PYTHONPATH
export PYTHONPATH=$SPARK_HOME/python/lib/py4j-0.10.4-src.zip:$PYTHONPATH
```
5. Проверить корректность установки можно с помощью следующего кода
```python
from pyspark import SparkContext
sc = SparkContext('local', 'test app')
a = range(10)
a = sc.parallelize(a)
print a.reduce(lambda x, y: x + y)
```
