Log Collector and Cost calculator.

1) To build -
mvn clean install
mvn dependency:copy-dependencies

2) To execute
Once the target folder is updated after the build move to target directory.
Execute : java -cp CostCalculation-1.0-SNAPSHOT.jar:dependency/jsch-0.1.53.jar Main

The flow of main.java will ask for several input file paths.

1) Do you want to read remote logs. Type Y or N
Y
2)Enter the server config file path
This file gives information of server ssh credentials, log file path
Structure :server address, username,password,log directory
eg: Contetn of file.
130.245.127.56,ubuntu,,/home/ubuntu/pinot/pinot-distribution/target/pinot-0.016-pkg/target/workloadData
3) Enter the Output Dir
Output dir path to fetch logs
4)Enter the public key file path or N if not required.
provide the .pem file location required for ssh.

4) Enter the logs directory based on which you want to calculate cost
Provide the destination log path directory which has all the consolidated logs.

5)Enter the table names config file
This file contains info about all the table names
eg Content of file
table1
table2
table3

6)Enter the Output file path for results.


Once the inputs are provided, the app calculated the cost and flushes the result in the specified result file.
Note: if you want to skip to cost calculation path directly say N to log collector part.