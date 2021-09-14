# ranger-docker [![Docker](https://github.com/takezoe/ranger-docker/actions/workflows/docker-publish.yml/badge.svg)](https://github.com/takezoe/ranger-docker/actions/workflows/docker-publish.yml)

Out of the box docker-compose for Apache Ranger. The current target version is Apache Ranger 2.1.0.

## How to run

Run ranger-admin, mysql, solr using docker-compose.

```
$ docker-compose up -d
```

Then, you can access ranger-admin at http://localhost:6080 ans sign-in with admin / ranger1234.

## How to build

To publish new ranger-admin docker image to [GitHub Packages](https://github.com/takezoe/ranger-docker/pkgs/container/ranger-docker%2Franger-admin), create a git tag like `v1.0.0`. GitHub Actions will build and publish a docker image automatically.
