# ranger-docker

Out of the box docker-compose for Apache Ranger. The current target version is Apache Ranger 2.1.0.

## How to run

Build Ranger's docker image. This will take a very long time.

```
$ docker-compose build
```

Run and open ranger-admin.

```
$ docker-compose up -d
```

Then, you can access ranger-admin at http://localhost:6080 ans sign-in with admin / ranger1234.
