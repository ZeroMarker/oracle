# oracle

docker pull container-registry.oracle.com/database/free

docker stop my_oracle_db

docker run -d -it --name my_oracle_db --env="ORACLE_SID=DB" --env="ORACLE_PDB=PDB" --env="ORACLE_PWD=password" -p 1521:1521 container-registry.oracle.com/database/free

docker rm my_oracle_db

docker rmi container-registry.oracle.com/database/free
--
[Oracle Database 23c Free — Developer Release for Java Developers with Docker on Windows](https://medium.com/oracledevs/oracle-database-23c-free-developer-release-for-java-developers-with-docker-on-windows-b164a7a61a91)

docker pull gvenzl/oracle-free

docker run -d --name oracle -p 1521:1521 -e ORACLE_PASSWORD=password -v oracle-volume:/opt/oracle/oradata gvenzl/oracle-free

docker ps -a

docker exec <container name|id> resetPassword <your password>

docker exec -it <container_name_or_id> /bin/bash

sqlplus / as sysdba

SELECT username FROM dba_users;

## connection
username: SYSTEM
password: password
Service Name: FREEPDB1

## ORACLE
[ORACLE](https://container-registry.oracle.com/ords/f?p=113:4:103233461092240:::4:P4_REPOSITORY,AI_REPOSITORY,AI_REPOSITORY_NAME,P4_REPOSITORY_NAME,P4_EULA_ID,P4_BUSINESS_AREA_ID:1863,1863,Oracle%20Database%20Free,Oracle%20Database%20Free,1,0&cs=3ExSLWuuuAENKM_WnrLNhJkwHauj70oyuBfWihQKXTP4hdbVgI2BhL91dVnLGt_6wqsGCZYSNy45mtwO4gUQYPA)

podman run --name <container name> \
-P | -p <host port>:1521 \
-e ORACLE_PWD=<your database passwords> \
-e ORACLE_CHARACTERSET=<your character set> \
-v [<host mount point>:]/opt/oracle/oradata \
container-registry.oracle.com/database/free:latest

docker run -d --name oracle -p 1521:1521 -e ORACLE_PASSWORD=password -v oracle-volume:/opt/oracle/oradata container-registry.oracle.com/database/free:latest