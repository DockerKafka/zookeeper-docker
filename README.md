zookeeper-docker
================

Dockerfile for [Apache ZooKeeper](https://zookeeper.apache.org/)

The image is available directly from [DockerHub](https://hub.docker.com/r/dockerkafka/zookeeper/)

You can browse the source in [GitHub](https://github.com/DockerKafka/zookeeper-docker)

## Usage

### Pull the image.
```sh
$ docker pull dockerkafka/zookeeper
```

### Start a server.
```sh
$  docker run -d --name kafkadocker_zookeeper_1  dockerkafka/zookeeper
```

### Connect to the server with zkshell.
```sh
$  docker run --rm -i -t --link kafkadocker_zookeeper_1:kafkadocker_zookeeper_1 dockerkafka/zookeeper zkCli.sh -server kafkadocker_zookeeper_1:2181
```

## Customization

Check out this repository, you will found the default Zookeeper configuration files under image/conf.

Start the container with the following line, so now you can modify the config in your host, and then start the server.
```sh
$  docker run -it --rm --volume `pwd`/image/conf:/opt/zookeeper-3.4.6/conf kafkadocker/zookeeper /bin/bash
```

After you finished the customization & testing of the config changes, build your own image.
```sh
$  docker build --tag="my-image" .
```


## Useful links

[ZooKeeper Administrator's Guide](http://zookeeper.apache.org/doc/r3.1.2/zookeeperAdmin.html)
