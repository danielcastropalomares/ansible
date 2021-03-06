# Source code

The real link of project it's from this URL:

https://github.com/robcowart/elastiflow/blob/master/INSTALL.md

# Requirements 

More info:
https://github.com/robcowart/elastiflow/blob/master/INSTALL.md


flows/sec | (v)CPUs | Memory | Disk (30-days) | ES JVM Heap | LS JVM Heap
---:|---:|---:|---:|---:|---:
250| 4 | 24 GB | 305 GB | 8 GB | 4 GB
1000| 8 | 32 GB | 1.22 TB  | 12 GB | 4 GB
2500| 12 | 64 GB | 3.05 TB | 24 GB | 6 GB

# Tested version:
* Elastic stack version 6.4
* Java openjdk-8
* Debian 9


# After installation:
1. Send netflow data from switch, router or firewall to IP elastiflow and port 2055 UDP.
2. Now acces to elastiflow via http://IP:5601, and create a new index : Management -> Index Patterns -> Create new index Patterns
3. Select "elastiflow-*" and timestamp
4. Import the dashboard from the github of the elastiflow "https://github.com/robcowart/elastiflow/archive/master.zip".
5. For import dashboard: Management -> Saves objects -> Import 

> BE PATIENT! The kibana and logstash it's started after 10-15 minutes 

You can check the state of services with the next commands:

kibana:
```
netstat -nltp | grep 5601
ps aux | grep kibana
/var/log/kibana/kibana.stdout or kibana.stderr
```
logstash:
```
ps aux | grep logstash
/var/log/logstash/logstash-plain.log
netstat -nlup | grep 2055
```
elastisearch
```
netstat -nltp | grep 9200
```
