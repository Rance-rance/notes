## gitlab

```shell
export GITLAB_HOME=/srv/gitlab

docker run --detach \
  --hostname github.exampe.com \
  --publish 10443:443 --publish 8080:80 --publish 8022:22\
  --name gitlab \
  --restart always \
  --volume $GITLAB_HOME/config:/etc/gitlab \
  --volume $GITLAB_HOME/logs:/var/log/gitlab \
  --volume $GITLAB_HOME/data:/var/opt/gitlab \
  --shm-size 256m \
  gitlab/gitlab-ee:latest
```

*default username:* `root`

*default password looked by these code:*
 `sudo docker exec -it gitlab grep 'Password:' /etc/gitlab/initial_root_password`

## openproject

```shell
docker run -it -p 8081:80 -d \
  --name openproject \
  -e OPENPROJECT_SECRET_KEY_BASE=secret \
  -e OPENPROJECT_HOST__NAME=localhost:8081 \
  -e OPENPROJECT_HTTPS=false \
  -v /srv/openproject/pgdata:/var/openproject/pgdata \
  -v /srv/openproject/assets:/var/openproject/assets \
  openproject/community:12
```

*default username:* `admin`

*default password:* `admin`

## portainer

```shell
docker run -p 8000:8000 -p 9443:9443 -d \
  --name portainer --restart=always \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v /srv/portainer/portainer_data:/data portainer/portainer-ce:latest
```

*go to the web site*

`http://[ip address]:8000`
or
`https://[ip address]:9443`


## penpot

```shell
curl -o docker-compose.yaml https://raw.githubusercontent.com/penpot/penpot/main/docker/images/docker-compose.yaml
```

*add `disable-secure-session-cookies` after `PENPOT_FLAGS` in `Backend` and `Frontend` in docker-compose.yaml*

```shell
docker compose -p penpot -f docker-compose.yaml up -d
```

## nginx
```shell
docker run --name nginx -p 80:80 -d nginx

cd /srv
sudo mkdir nginx && cd nginx
sudo mkdir conf && sudo mkdir html && sudo mkdir log

sudo docker cp nginx:/etc/nginx/conf.d /srv/nginx/conf
sudo docker cp nginx:/etc/nginx/nginx.conf /srv/nginx/conf/nginx.conf
sudo docker cp nginx:/usr/share/nginx/html/index.html /srv/nginx/html/index.html

docker rm -f nginx

docker run -d -p 80:80 --name nginx \
-v /srv/nginx/conf/conf.d:/etc/nginx/conf/d \
-v /srv/nginx/conf/nginx.conf:/etc/nginx/nginx.conf \
-v /srv/nginx/html/index.html:/user/share/nginx/html/index.html \
-v /srv/nginx/log/:/var/log/nginx \
nginx
```

*reload nginx*

```shell
docker exec -it ngnix nginx -s reload
```

## traefik

## influxdb

## telegraf

## grafana

## fatediel/frpc|frps

## clash

## files