
# Research:
* [https://docs.gitlab.com/ee/ci/yaml/#coverage](https://docs.gitlab.com/ee/ci/yaml/#coverage) - Config file
* [https://docs.gitlab.com/ee/user/project/pipelines/job_artifacts.html](https://docs.gitlab.com/ee/user/project/pipelines/job_artifacts.html) - How to export results


To register a new gitlab-runner with custom certificate:
```
gitlab-runner register -n \
  --tls-ca-file=/tmp/ca-files/ca_bundle.crt \
  --url=https://gitlab.example.com/ \
  --registration-token=xxxxxxxxxx \
  --name=shared-runner-1 \
  --run-untagged=true \
  --locked=false \
  --executor=docker
  --docker-image=node:8.10.0
```
