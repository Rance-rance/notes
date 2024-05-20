
## docker run commands
```shell
docker run -d -p 35001:8080 --name crop --network overlay -e pwd=password  hub.stdup.cn/crop:latest

docker run -d -p 3001:8080 --name dkron --network overlay  --label traefik.enable=true --restart always  dkron/dkron:3.2.7 'agent' '--server' '--bootstrap-expect=1' '--node-name=sts1'
```
