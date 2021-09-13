# ranger-docker

Out of the box docker-compose for Apache Ranger. The current target version is Apache Ranger 2.1.0.

## How to run

Run ranger-admin, mysql, solr using docker-compose.

```
$ docker-compose up -d
```

Then, you can access ranger-admin at http://localhost:6080 ans sign-in with admin / ranger1234.

## How to build

While community docker images are used for mysql and solr, ranger-admin is built and published by GitHub Actions automatically.

To publish new ranger-admin docker image to [GitHub Packages](https://github.com/takezoe/ranger-docker/pkgs/container/ranger-docker%2Franger-admin), create a git tag like `v1.0.0`.
