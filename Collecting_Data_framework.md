Collecting Data framework
============

## Model
### User Information Organizing

    Name
    User Name
    email
    location
    public / private profile
    Gender
    Male
    Female
    Other
    Age Range
    Occupation
    Spouse’s Occupation
    Marital Status
    activities entries
    image category entries
    image-net.org/api/text/imagenet.bbox.obtain_synset_wordlist
    relevant to adwords
    text category entries
    Codes and Formats  |  AdWords API  |  Google Developers
    relevant to adwords
        Topics used for personalised ads - Ads Help
    Index of /blog/attachments

### ElasticSearch Entries

    user id
    activities entries
    image category entries
    text category entries

### Good readings

 * [How to integrate Elastic Search with MongoDB](https://medium.com/@ironico/how-to-integrate-elastic-search-with-mongodb-7bff7fdd3cf5#.607bj1d82)

## Docker

### Install on Ubuntu
[Install Docker engine 1](https://docs.docker.com/engine/installation/linux/ubuntulinux/)
[Install Docker engine 1](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04)

1. Update package information, ensure that APT works with the https method, and that CA certificates are installed.
```
    $ sudo apt-get update
    $ sudo apt-get install apt-transport-https ca-certificates
```
2. Add the new GPG key.
```
    $ sudo apt-key adv \
               --keyserver hkp://ha.pool.sks-keyservers.net:80 \
               --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
```
3. Run the following command, substituting the entry for your operating system for the placeholder <REPO>.
```
    $ echo "<REPO>" | sudo tee /etc/apt/sources.list.d/docker.list
Notice: <REPO>
    * Precise 12.04 (LTS) deb https://apt.dockerproject.org/repo ubuntu-precise main
    * Trusty 14.04 (LTS)  deb https://apt.dockerproject.org/repo ubuntu-trusty main
    * Wily 15.10  deb https://apt.dockerproject.org/repo ubuntu-wily main
    * Xenial 16.04 (LTS)  deb https://apt.dockerproject.org/repo ubuntu-xenial main
```
4. Verify that APT is pulling from the right repository.
```
    $ apt-cache policy docker-engine
      docker-engine:
        Installed: 1.12.2-0~trusty
        Candidate: 1.12.2-0~trusty
        Version table:
       *** 1.12.2-0~trusty 0
              500 https://apt.dockerproject.org/repo/ ubuntu-trusty/main amd64 Packages
              100 /var/lib/dpkg/status
           1.12.1-0~trusty 0
              500 https://apt.dockerproject.org/repo/ ubuntu-trusty/main amd64 Packages
           1.12.0-0~trusty 0
              500 https://apt.dockerproject.org/repo/ ubuntu-trusty/main amd64 Packages
```
5. Install the recommended packages.
```
    $ sudo apt-get install linux-image-extra-$(uname -r) linux-image-extra-virtual
```
6. Install Docker.
```
    $ sudo apt-get install docker-engine
```
7. Run Docker.
```
    $ sudo service docker start
```
8. Verify Docker
```
    $ sudo docker run hello-world
```

### Start basic Docker
[Reference](https://scotch.io/tutorials/getting-started-with-docker)

### Build Docker image 
[Reference](https://docs.docker.com/engine/getstarted/step_four/)

### Commit Docker Container
```
docker commit --change='CMD ["bash"]' -c "EXPOSE 3000" 5038f152f973 loopback/follu
```

## MongoDB
* [Installation](https://docs.mongodb.com/getting-started/shell/tutorial/install-mongodb-on-ubuntu/#install-mongodb-community-edition)
* [Install MongoDB from source](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-linux/)
* [Getting Started with MongoDB](https://code.tutsplus.com/tutorials/getting-started-with-mongodb-part-1--net-22879)
* [Tutorial](http://www.guru99.com/mongodb-tutorials.html)

### Install MongoDb on Docker
* [Docker tutorial](https://docs.docker.com/engine/examples/mongodb/)
* [Dockerize MongoDB](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04#step-1-%E2%80%94-installing-docker)

### How to start MongoDB docker
* Start docker
```
docker run -it <mongo_image_name> /bin/bash
or
sudo docker run -p 28001:27017 -it mongodb-test bash (port 28001 is a port used for conntecing to container)
``` 
* Connect to Container
```
mongo -p 28001
```

### Setting up MongoDB sync to Elasticsearch
* [5 ways to synchronize data from MongoDb to ElasticSearch](https://www.linkedin.com/pulse/5-way-sync-data-from-mongodb-es-kai-hao)
* [How To Sync Transformed Data from MongoDB to Elasticsearch with Transporter](https://www.digitalocean.com/community/tutorials/how-to-sync-transformed-data-from-mongodb-to-elasticsearch-with-transporter-on-ubuntu-14-04)
* [Using MongoDB with Elasticsearch: Mongo-Connector](http://madhacker.me/use-mongodb-and-elasticsearch-2/)
* [how-to-use-mongo-connector-with-elasticsearch](https://blog.jixee.me/how-to-use-mongo-connector-with-elasticsearch/)
```
mongod --replSet "rs0"
mongo
rs.initiate()
rs.conf()
pip install elastic-doc-manager[elastic2]
pip install mongo-connector
mongo-connector -m localhost:27017 -t localhost:9200 -d elastic2_doc_manager -v 
mongo-connector -m 172.33.47.10:28001 -t 172.33.47.10:28002 -d elastic2_doc_manager -v
```
```
Note:
Elasticsearch 1.x                   pip install 'mongo-connector[elastic]'
Amazon Elasticsearch 1.x Service    pip install 'mongo-connector[elastic-aws]'
Elasticsearch 2.x                   pip install 'mongo-connector[elastic2]'
Amazon Elasticsearch 2.x Service    pip install 'mongo-connector[elastic2-aws]'
Elasticsearch 5.x                   pip install 'mongo-connector[elastic5]'
```

## Elasticsearch
* [How To Install and Configure Elasticsearch on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-elasticsearch-on-ubuntu-16-04)
* [Dockerize Elasticsearch](https://www.elastic.co/blog/how-to-make-a-dockerfile-for-elasticsearch)
* [Configuration](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-elasticsearch-on-ubuntu-16-04)
* [Tutorial](http://joelabrahamsson.com/elasticsearch-101/)

### How to run Docker Elasticsearch
* Start docker
```
sudo docker run -p 28002:9200 elastic-test
```
* Connect to container
```
curl -X GET 'http://172.33.47.10:28002'
```

## Redis

* [Install](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-redis)
* [Dockerize a Redis service](https://docs.docker.com/engine/examples/running_redis_service/)

### How to run Docker Redis
* Start docker
```
sudo docker run -p 28003:6379 redis-test
```

## Loopback

* [Install]()