# How to restart:

1. Figure out where your vagrant folder is by searching your own computer
2. Copy the path
3. Open Command Prompt
4. Type in: 

   ```text
   cd (paste path here)
   vagrant up
   vagrant ssh
   ```

5. Then type in:

   ```text
   bash ~/hadatac-blazegraph/jetty-distribution-9.4.12.v20180830/bin/jetty.sh start
   bash ~/hadatac-solr/solr/run_solr6.sh start
   cd ~/hadatac
   sbt run
   ```

6. Go to [http://localhost:9000/hadatac/](http://localhost:9000/hadatac/) 

