# Aleph docker

## pre-requisites
* Docker & Docker-compose (latest version)


## Install

```git clone --recursive http://github.com/pr0teus/aleph-docker.git```

```cd aleph-docker```

Confiure o Aleph de acordo com o github do Merces(@mentebinaria) [merces/aleph](http://github.com/merces/aleph.git) no path:

```
$ aleph/settings.py
```

## Run
```
$ docker-compose build
```

```
$ docker-compose -d up aleph-server aleph-webui elasticsearch kibana
```

Now you can visit http://localhost:5000

| User  | Password    |
|-------|-------------|
| admin | changeme12! |

Then you can see more things at kibana http://localhost:5601
Any files placed under
aleph/temp will be analyzed by Aleph pipeline.

All samples will be stored @ aleph/samples

## Todo
* Add Elasticsearch mapping
* Add Kibana graphs/dashboards
* Add Cuckoo docker & integrate
