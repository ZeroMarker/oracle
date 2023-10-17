# oracle

docker pull container-registry.oracle.com/database/free

docker stop my_oracle_db

docker run -d -it --name my_oracle_db --env="ORACLE_SID=DB" --env="ORACLE_PDB=PDB" --env="ORACLE_PWD=password" -p 1521:1521 container-registry.oracle.com/database/free

docker rm my_oracle_db

docker rmi container-registry.oracle.com/database/free
--
[Oracle Database 23c Free — Developer Release for Java Developers with Docker on Windows](https://medium.com/oracledevs/oracle-database-23c-free-developer-release-for-java-developers-with-docker-on-windows-b164a7a61a91)

docker pull gvenzl/oracle-free

docker run -d -n oracle -p 1521:1521 -e ORACLE_PASSWORD=password -v oracle-volume:/opt/oracle/oradata gvenzl/oracle-free

docker exec <container name|id> resetPassword <your password>