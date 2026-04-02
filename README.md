# Max-Temperature-MapReduce-Cloudera
This project demonstrates a Max Temperature MapReduce program using Hadoop in Cloudera. It processes weather data to identify temperature patterns using distributed computing.


🌡️ MaxTemperature MapReduce Execution (Cloudera)

1. Start Cloudera services
   sudo service cloudera-scm-server start
   sudo service cloudera-scm-agent start

2. Verify HDFS access
   hdfs dfs -ls /

3. Create working directory
   cd ~
   mkdir weather_mr
   cd weather_mr

4. Create Java program
   nano MaxTemperature.java

5. Create input dataset
   nano weather.txt

6. Compile the program
   javac -classpath `hadoop classpath` -d . MaxTemperature.java

7. Verify compiled files
   ls

8. Create JAR file
   jar -cvf MaxTemperature.jar *

9. Verify JAR creation
   ls

10. Create input directory in HDFS
    hdfs dfs -mkdir tempinput

11. Upload dataset to HDFS
    hdfs dfs -put weather.txt tempinput

12. Verify upload
    hdfs dfs -ls tempinput

13. Execute MapReduce job
    hadoop jar MaxTemperature.jar MaxTemperature tempinput tempoutput

14. View output
    hdfs dfs -cat tempoutput/part-r-00000
