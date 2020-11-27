# Spring-boot-db2-example by Corasaniti

# prerequisites
An instance of DB2 installed on a server.  
For development it's recommended that you install DB2 Docker image provided by IBM in the Docker registry.

Use the following command to run the DB2 instance on Docker after installing Docker Engine on your system.

```
docker run -itd --name mydb2 --hostname mydb2 --privileged=true \
-p 50000:50000 \
-e LICENSE=accept \
-e DB2INST1_PASSWORD=DB2INST1 \
-e DBNAME=testdb \
-v /your/storage/path/data:/database \
ibmcom/db2
```

<br/>

# setup-project 
In application.properties file set Datasource by setting DB2 properties

```
spring.datasource.url=jdbc:db2://YOUR_DB_IP_SERVER:50000/TESTDB
spring.datasource.username=DB2INST1
spring.datasource.password=DB2INST1
```

<br/>

# prepare-db2-database 
Exexute this SQL script from script-slq folder

```
01_CREATE_PRODUTCT.sql
```
<br/>

# run-the-project
```
mvn spring-boot:run
```

<br/>

# test-api-rest-from-browser
```
Product List
http://localhost:8080/product/list

Show Product {id}
http://localhost:8080/product/show/{id}
http://localhost:8080/product/show/1
http://localhost:8080/product/show/2

New Product
http://localhost:8080/product/new

Edit Product {id}
http://localhost:8080/product/edit{id}
http://localhost:8080/product/edit/1
http://localhost:8080/product/edit/2

Delete Product {id}
http://localhost:8080/product/delete/{id}
http://localhost:8080/product/delete/1
http://localhost:8080/product/delete/2
```