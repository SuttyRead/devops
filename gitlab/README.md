https://docs.gitlab.com/ee/install/docker.html

```
sudo docker exec -it bbc0e33a63d2 grep 'Password:' /etc/gitlab/initial_root_password
```
kWHHHaFVwhSMvvDmfHkM9ZNel/I0Rwi4LADPFe2IqEY=

gitlab runner:
https://docs.gitlab.com/runner/install/docker.html
```
docker run -d --name gitlab-runner --restart always \
  -v /srv/gitlab-runner/config:/etc/gitlab-runner \
  -v /var/run/docker.sock:/var/run/docker.sock \
  gitlab/gitlab-runner:latest
```

https://docs.gitlab.com/runner/register/index.html?tab=Docker
```
docker run --rm -it -v /srv/gitlab-runner/config:/etc/gitlab-runner gitlab/gitlab-runner register
```