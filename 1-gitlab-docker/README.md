# Gitlab Docker

ref https://www.youtube.com/watch?v=BTSf2OoFyqE

ref doc https://docs.gitlab.com/ee/install/docker.html

```
sudo docker run --detach \
  --hostname gitlab.example.com \
  --publish 8443:443 --publish 8880:80 --publish 8822:22 \
  --name gitlab \
  --restart always \
  --volume /srv/gitlab/config:/etc/gitlab \
  --volume /srv/gitlab/logs:/var/log/gitlab \
  --volume /srv/gitlab/data:/var/opt/gitlab \
  --shm-size 256m \
  gitlab/gitlab-ee:latest
```

Xem log cua Gitlab

```
sudo docker logs -f gitlab
```

Lay mat khau root cua Gitlab

```
sudo docker exec -it gitlab grep 'Password:' /etc/gitlab/initial_root_password
```