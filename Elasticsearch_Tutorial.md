Elasticsearch Tutorial
============

## Good readings

* [How To Install and Configure Elasticsearch on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-elasticsearch-on-ubuntu-16-04#prerequisites)
* [Elastic Reference](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)
* [Beginner's Guide to ElasticSearch](https://www.codementor.io/javascript/tutorial/getting-started-with-elasticsearch)
* [Elasticsearch tutorial](http://logz.io/blog/elasticsearch-tutorial/)
* [Elasticsearch Query Tutorial](http://okfnlabs.org/blog/2013/07/01/elasticsearch-query-tutorial.html)
* [Getting started with Elastcisearch](https://www.codementor.io/javascript/tutorial/getting-started-with-elasticsearch)
* [Javascript for ElasticSearch](https://www.elastic.co/guide/en/elasticsearch/client/javascript-api/current/about.html)
* [Build a Search Engine with Node.js and Elasticsearch](https://www.sitepoint.com/search-engine-node-elasticsearch/)
* [Getting started with Elasticsearch and Node.js](https://www.compose.com/articles/getting-started-with-elasticsearch-and-node/)

## Install

## Configure

## Terms

| MySQL (RDBMS) Terminology | ElasticSearch Terminology |
|---------------------------|---------------------------|
| Database                  | Index                     |
| Table                     | Type                      |
| Row                       | Document                  |


## Basic Usages
```
REST API Format : http://host:port/[index]/[type]/[_action/id]

HTTP Methods used: GET, POST, PUT, DELETE
```
To get a list of all available indices in your ElasticSearch, use the following URL :
> http://localhost:9200/_cat/indices

To get the status of an index (say, a company), use the following URL:
> http://localhost:9200/company?pretty

### Get database information
```
    $> curl 'localhost:28002/_cat/indices?v'
```

### Inserting Data
```
	$> curl -X GET 'http://localhost:9200' 
	$> curl -XGET 'http://localhost:9200/_nodes?pretty'
```

### Retrieve Data
```
	$> curl -X POST 'http://localhost:9200/tutorial/helloworld/1' -d '{ "message": "Hello World!" }'
	$> curl -X GET 'http://localhost:9200/tutorial/helloworld/1'
```

### Retrieving Data with Conditional Search
```
$> curl -X GET http://127.0.0.1:9200/logs/_search
```

```
$> curl -X GET http://127.0.0.1:9200/logs/_search -d '{
> "query": {
> "match_phrase": {
> "message": "User logged in"
> }
> }
> }'
```

### Modify data
```
	$> curl -X PUT 'localhost:9200/tutorial/helloworld/1?pretty' -d '
	$> {
  	$> "message": "Hello People!"
	$> }'
```

### Delete Data
```
$> curl -X DELETE http://127.0.0.1:9200/app/users/4
    {
    "_id": "4",
    "_index": "app",
    "_shards": {
    "failed": 0,
    "successful": 1,
    "total": 2
    },
    "_type": "users",
    "_version": 2,
    "found": true
    }
```

__You can delete items by specifying a query:__
```
$> curl -X DELETE 'http://127.0.0.1:9200/app/users/_query?q=username:john'
    {
    "_id": "_query",
    "_index": "app",
    "_shards": {
    "failed": 0,
    "successful": 1,
    "total": 2
    },
    "_type": "users",
    "_version": 1,
    "found": false
    }
```