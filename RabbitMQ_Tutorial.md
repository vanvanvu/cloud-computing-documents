RabbitMQ Tutorial
============
## Good readings
* [RabbitMQ Tutorials](https://www.rabbitmq.com/getstarted.html)
* [Pika lib](https://pika.readthedocs.io/en/0.10.0/index.html)
* [Code tutorials](https://github.com/rabbitmq/rabbitmq-tutorials)
* [How To Install and Manage RabbitMQ ](https://www.digitalocean.com/community/tutorials/how-to-install-and-manage-rabbitmq)
* [RabbitMQ for 2015-05-18-part1-rabbitmq-for-beginners-what-is-rabbitmqners](https://www.cloudamqp.com/blog/2015-05-18-part1-rabbitmq-for-beginners-what-is-rabbitmq.html)

## Terms
__Producer__: Application that sends the messages.
__Consumer__: Application that receives the messages.
__Queue__: Buffer that stores messages.
__Message__: Information that is sent from the producer to a consumer through RabbitMQ.
__Connection__: A connection is a TCP connection between your application and the RabbitMQ broker.
__Channel__: A channel is a virtual connection inside a connection. When you are publishing or consuming messages from a queue - it's all done over a channel.
__Exchange__: Receives messages from producers and pushes them to queues depending on rules defined by the exchange type. In order to receive messages, a queue needs to be bound to at least one exchange.
__Binding__: A binding is a link between a queue and an exchange.
__Routing key__: The routing key is a key that the exchange looks at to decide how to route the message to queues. The routing key is like an address for the message.
__AMQP__: AMQP (Advanced Message Queuing Protocol) is the protocol used by RabbitMQ for messaging.
__Users__: It is possible to connect to RabbitMQ with a given username and password. Every user can be assigned permissions such as rights to read, write and configure privileges within the instance. Users can also be assigned permissions to specific virtual hosts.
__Vhost, virtual host__: A Virtual host provide a way to segregate applications using the same RabbitMQ instance. Different users can have different access privileges to different vhost and queues and exchanges can be created so they only exists in one vhost.

## Install
* [RabbitMQ Installation](https://www.rabbitmq.com/install-debian.html)

### Install RabbitMQ Library 
__Python__
```
sudo pip install pika
```

__Nodejs__
```
npm install amqplib --save
```

### Dockerize RabbitMQ

## Configure

## Usage
```
rabbitmqctl list_vhosts
rabbitmqctl list_queues -p <vhost>

rabbitmqctl cluster_status

rabbitmqctl stop_app
rabbitmqctl join_cluster <node>
rabbitmqctl start_app

rabbitmqctl report    # Dump detailed report on RabbitMQ instance  
```