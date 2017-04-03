# SolrCloud

### Running SolrCloud

### 1.- Downloading the repository
```
    git clone https://github.com/gerald-axel/SolrCloud.git
    cd SolrCloud
```
### 2.- Running SolrCloud
```
    docker-compose up -d
```
### 3.- Creating a collection

```
    docker exec -it solrcloud_solr1 bin/solr create_collection -c collectionName -shards 2 -p 8983
```

### Persisting data on volumes
- SolrCloud

The information of each instance of Solr is being storage on separated volumes.

| Folder Directory                             | Description                                                  |
| -------------------------------------------- | ------------------------------------------------------------ |
|  /opt/solr/server/solr                       | Collections or Cores data.                                   |


- Zookeper

To keep synchronized the SolrCloud is necessary that zookeeper store the information of its own configuration with the other Solr instances and a log of the transactions made it so far.

| Folder Directory                                         | Description                                      |
| -------------------------------------------- | ------------------------------------------------------------ |
|  /conf                                       | Information about how zookeeper is connected with the SolrCloud.  |
|  /data                                       | The collections that had been created on the SolrCloud.          |
|  /datalog                                    | Information about the transactions between each Solr instance. |


