# Microservice Jobber


## Control
1. ok
2. ok
3. ok
4. Tools docker ---- ok
5. Microservices helper library   --- friday

## Commands
`docker compose up -d redis mongodb mysql postgres rabbitmq elasticsearch kibana`

## Problems

1. 'Node locked'
 Message: "org.elasticsearch.bootstrap.StartupException: java.lang.IllegalStateException: failed to obtain node locks, tried [[C:\Elastic_search_cluster\data\elastic_search_cluster]] with lock id [0]; maybe these locations are not writable or multiple nodes were started without increasing [node.max_local_storage_nodes] (was [1])?"
 Solution:
In my case, I had to go to docker on "elastic-search" and tab "exec" and then navigated to "share/elast../data", but it only have permission root, because this folder was created by root, and the user "elastic" not have permision to write, so I run this command "chmod -R 777 data", I think its a fast solution but in production mode maybe it will get some problems.