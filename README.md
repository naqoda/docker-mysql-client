# Info
Based on official [centos] (https://hub.docker.com/_/centos/) images with addition of:

- MySQL client

# Run
## Run a query

```console
docker run --rm \
    naqoda/mysql-client \
    mysql --host=example.com --user=root --password=123321 --database=test --execute='show tables;'
```

## Dump a database

```console
docker run --rm \
    naqoda/mysql-client \
    mysqldump --host=example.com --user=root --password=123321 test
```

## Dump a database without specifying user and password on the command line

```console
docker run --rm \
	-v /local/path/to/my.cnf:/var/lib/mysql/my.cnf \
    naqoda/mysql-client \
    mysqldump --defaults-extra-file=/var/lib/mysql/my.cnf test
```

