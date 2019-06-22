# Docker file for Elastic Stack

[Home](../README.md) > [Elastic Stack](README.md)

## References

- [github.com/elastic/stack-docker](https://github.com/elastic/stack-docker)
- [Logstash Redis input plugin](https://www.elastic.co/guide/en/logstash/current/plugins-inputs-redis.html)

## Usage

## Prerequisites

- `docker-compose` must be available
- The file path must be shared on Docker (D: drive for example)

### Start the whole thing

```dos
docker-compose up
```

Open:

- Elasticsearch [127.0.0.1:9200](http://127.0.0.1:9200/)
- Kibana at [localhost:5601](http://localhost:5601/)

### Stop

```dos
docker-compose down
```

### Clean

```dos
docker-compose down --volumes --remove-orphans
```
