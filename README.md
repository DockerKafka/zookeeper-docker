zookeeper-docker
================

## Usage

Pull the image.
```sh
$ docker pull dockerkafka/zookeeper
```

Start a server.
```sh
$  docker run -d --name myZookeeper  dockerkafka/zookeeper
```

Connect to the server with zkshell.
```sh
$  docker run --rm -i -t --link myZookeeper:myZookeeper dockerkafka/zookeeper zkCli.sh -server myZookeeper:2181
```

## Customization

Check out this repository, you will found the default Zookeeper configuration files under image/conf. Modify them and run
```sh
$  docker-compose up
```

## Useful links

[ZooKeeper Administrator's Guide](http://zookeeper.apache.org/doc/r3.1.2/zookeeperAdmin.html)
