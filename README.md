# spring-cloud-eureka-ha

## Reference Link 
https://medium.com/swlh/spring-cloud-high-availability-for-eureka-b5b7abcefb32

## Starting Up Eureka Server Cluster and Client on Local Machine
In order to start this entire cluster in your local machine, you will have to do some additional configurations in C:\Windows\System32\drivers\etc\hosts file.

### Step 1 :
Need to add the below entries. This will allow you to access peer-1-server.com , peer-2-server.com and peer-3-server.com host names in your local machine.

`127.0.0.1 peer-1-server.com`

`127.0.0.1 peer-2-server.com`

`127.0.0.1 peer-3-server.com`

### Step 2 : Start the Eureka Server 
After successfull build of Eureka Server, Navigate to <eureka_server_root_directory>/target folder via three different command prompts and and execute the below three commands separately in each command prompt. 

This will start three instance of Eureka server in peer-1 , peer-2 and peer-3 profiles

`java -jar -Dspring.profiles.active=peer-1 eureka-server-1.0.0-SNAPSHOT.jar`

`java -jar -Dspring.profiles.active=peer-2 eureka-server-1.0.0-SNAPSHOT.jar`

`java -jar -Dspring.profiles.active=peer-3 eureka-server-1.0.0-SNAPSHOT.jar`

Hit the below URLS:

`http://peer-1-server.com:9001/`
`http://peer-2-server.com:9002/`
`http://peer-3-server.com:9003/`
