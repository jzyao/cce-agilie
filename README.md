# cce-agilie

## 手动LB
节点跑
```
docker run --detach \
  --name cce-lb \
  --restart=unless-stopped \
  --publish 80:80 \
  --publish 443:443 \
  --publish 5443:5443 \
  --publish 9443:9443 \
  --publish 4134:4134 \
  --privileged=true \
  --volume ${PWD}/nginx.conf:/etc/nginx/nginx.conf:ro \
  nginx:stable-alpine
```

## gitlab
节点创几个文件夹，然后跑
```
docker-copose -f gitlab.yaml
```
