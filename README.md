# spring-boot-db2-example

# Prerequisites
An instance of DB2 installed on a server.  
For development it's recommended that you install DB2 Docker image provided by IBM in the Docker registry.



Use the following command to run the DB2 instance on Docker after installing Docker Engine on your system.

<pre><code>docker run -itd --name mydb2 --hostname mydb2 --privileged=true -p 50000:50000 -e LICENSE=accept -e DB2INST1_PASSWORD=DB2INST1 -e DBNAME=testdb -v /your/storage/path/data:/database ibmcom/db2</code></pre>
