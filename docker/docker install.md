## install docker engine on ubuntu 22.04

The most convenient way to install docker engine on ubuntu is install using the convenience script

```shell
$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sudo sh get-docker.sh
```

If you receive errors when trying to run without root, create the docker group and add your user:
```shell
$ sudo groupadd docker
$ sudo usermod -aG docker $USER
```

install docker-compose
```shell
$ sudo apt-get install docker-compose-plugin
```

don't run docker daemon as a non-root user