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
docker-compose -f gitlab.yaml
docker exec –it gitlab /bin/bash
vim /etc/gitlab/gitlab.rb
修改  "external_url ‘http://114.115.139.45’ ; gitlab_rails['gitlab_shell_ssh_port'] = 2022"
gitlab-ctl reconfigure
```
