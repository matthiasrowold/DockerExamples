# Docker and Continuous Integration

## GitLab Runner Docker image
https://docs.gitlab.com/runner/install/docker.html

There is a docker image of the standard GitLab runner. In general every GitLab Runner command like `gitlab-runner <some runner commands>`can be executed with `docker run <docker options> gitlab/gitlab-runner <some runner commands>

While starting the runner, a volume (https://docs.docker.com/storage/) must be mounted into the gitlab-runner container. This is needed for configs and other recources.
```
docker run -d --name gitlab-runner --restart always \
  -v /srv/gitlab-runner/config:/etc/gitlab-runner \
  -v /var/run/docker.sock:/var/run/docker.sock \
  gitlab/gitlab-runner:latest
```
Afterwards you have to register the runner: https://docs.gitlab.com/runner/register/index.html#docker

