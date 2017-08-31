# redis容器创建

```
docker run -d -v /etc/localtime:/etc/localtime:ro \
        -p 6379:6379 \
        --name 容器名 \
        redis redis-server --appendonly yes
```

# mysql容器创建

```
docker run -d -v /etc/localtime:/etc/localtime:ro \
        -e MYSQL_ROOT_PASSWORD=mysql密码 \
        -p 3306:3306 \
        --name 容器名称 \
        mysql
```

# postgres容器创建

```
docker run -d -v /etc/localtime:/etc/localtime:ro \
        -e POSTGRES_PASSWORD=postgres密码 \
        -p 5432:5432 \
        --name 容器名称 \
        postgres
```

# rabbitmq容器创建

```
docker run -d -v /etc/localtime:/etc/localtime:ro \
        -e RABBITMQ_ERLANG_COOKIE='cookie值' \
        -p 5672:5672 \
        -p 15672:15672 \
        --hostname 主机名(集群时需要) \
        --name 容器名 \
        rabbitmq:3.6.1-management
```

# elasticsearch容器创建

```
docker run -d -v /etc/localtime:/etc/localtime:ro \
        -p 9200:9200 \
        -p 9300:9300 \
        --name 容器名 \
        elasticsearch
```

# kibana容器创建

```
docker run -d -v /etc/localtime:/etc/localtime:ro \
        -p 5601:5601 \
        --link some-elasticsearch:elasticsearch \
        --name 容器名 \
        kibana
```

> -e ELASTICSEARCH_URL=http://some-elasticsearch:9200  
> 可以通过 **ELASTICSEARCH_URL** 指定外部地址

# mongo容器穿件

```
docker run -d -v /etc/localtime:/etc/localtime:ro \
        -p 27017:27017 \
        --name 容器名 \
        mongo
```
