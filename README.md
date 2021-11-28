# 5_3_Logging_Reporting

1. List some logging and visualization tools available in the market with the preferred senario to use one over other.

Some of the logging tools are:
==> ELK stack: It is the combination of ElasticSearch, Logstash and Kibana: a complete stack for logging and visualization which helps to process and analyze the logging data easily. 
Elastic search helps users to find matches within datasets using a wide range of query languages. It is a high speed search and analytics engine which can be expanded into multiple clusters of server nodes and easily handles gigantic volumes of data. Kibana is a visualization tool which helps users to analyze their data and build reports with ease. Logstash is an open source, server side data processing pipeline that enables to ingest data from multiple sources simultaneously and enrich and transform it before indexed to ElasticSearch and used to aggregate and process data and send it to elastic search.
The reason to use this stack are:
It allows us to monitor apps built on open source installation, web servers and database logs. 
It provides efficient log tracking and database management and visualization.

==> Graylog:
It is an open source centralized log management service that allows quick analyzing of logs. It is also easy to scale. It provides an easy to use interface and robust functionality. 
Its built in fault tolerance can run multithreaded searches which helps us to analyze several potential threats together.

==> Nagios:
It simplifies data collection and information and makes it more accessible to system administrators. 
It captures data in real time and feeds it to powerful search tools.
It can audit a range of network related events and helps to automate the distribution of alerts.
It can run predefined scripts if certain conditions are met which helps in automation in problem solving.
It can filter log data based on geographical location which helps to build dashboards with mapping technology which helps to understand flow of web traffic.

==> LOGalyze
It is designed to work as a massive pipeline in which multiple servers, apps and network devices can feed information using Simple Object Access Protocol (SOAP).
It provides a front end interface to monitor, collect and analyze data.
It allows the gathering of audit data in format required by regulatory acts.

==> Fluentd
It is a robust, open source tool for data collection which is compatible with most common technology tools available.
It decouples data sources from backend systems by providing a unified logging layer in between. 
It can extend your logging data into other apps and drive better analysis from it with minimal effort.

==> Octopussy
It is an open source tool which helps to analyze logs from different networking devices (like routers, firewalls, load balancers etc) and all their applications and services supporting syslog protocol.
It sends alert messages via email and other open source instant messengers which helps to be updated to what is going on with the system.
It provides a free solution to prevent system outages, security threats and application errors.




2. Mention 10 best practises when logging. Why is log formatting necessary?

The best practices while logging are:
==> Choose specific goals: 
Choosing specific goals while logging helps to make efficient decisions and easy to extract information from generated logs.

==> Follow proper standards: 
Using standard log frameworks helps to control the amount of details included in logs, define levels of alert and implement log rotation policies.

==> Make accessible log routine: 
Using standard date and time format and providing appropriate log context helps to understand logs more easily.

==> Make sure that logs are helpful: 
Important log records should be highlighted if possible and meaningful log messages should be written. Like Operation Incomplete, Database Unreachable and so on.

==> Create logging standards and structure: 
The logging structure must be consistent and all logs should show the timestamp and name of host and logger.

==> Use proper error severity levels: 
The log levels should be properly mentioned like: FATAL, ERROR, WARN, INFO, DEBUG, TRACE ALL or OFF. It helps us to focus on what is important and what is not.

==> Provide appropriate details: 
The details in log messages must be appropriate, i.e. Not too much and no less. Saving too much log details will make it difficult to focus on what is important and Saving less details may miss some important information.

==> Use of tools to manage logs: 
Use of tools can help in automation and ease in managing logging information like managing log data, provides a way to search and filter log messages. Use of UI helps in visualization of data more easily.

==> Do not log sensitive information: 
Sensitive information like passwords, credit card informations and social security numbers must not be logged. It may expose certain vulnerabilities to the system. 

==> Log in machine parsable format: 
Logging in machine parsable format like JSON helps us to easily evaluate the logged details and can be easily processed by existing tools.







3. Create a file in your system. Whenever a someone performs some action(read, write, execute) on that file, the event should be logged somewhere. 

4. install logstash in your system. download a sample nginx log from https://github.com/elastic/examples/blob/master/Common%20Data%20Formats/nginx_logs/nginx_logs , parse the logs using logstash. The parsed output must contain the geogriphical information like country, state etc. that the request is originating from. save the parsed output to a file in your system.

The used commands are:

To install logstash:

==> wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list

==> sudo apt-get update && sudo apt-get install logstash

To start logstash:
==> Sudo systemctl start logstash
To check the status:
==> Sudo systemctl status logstash

Java runtime environment is installed:
==> Sudo apt install default-jre

In the directory /etc/logstash/conf.d a file is made, logstash.conf:
==> Cd /etc/logstash/conf.d
==> Nano logstash.conf

To parse logs:
==> Cd /usr/share/logstash/bin
==> Sudo ./logstash --path.settings /home/bj/logtest/log --path.data sensor39 -f /etc/logstash/conf.d/


