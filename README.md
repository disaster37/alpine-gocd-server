alpine-gocd-server
===============

This image permit run GoCD Server.

## How use it


```bash
docker run -d --name gocd-server \
  -v $PWD/data/gocd-server:/data \
  -p 8153:8153 \
  webcenter/alpine-gocd-server:latest
```

Or use docker-compose:
```bash
docker-compose up
```



### Parameters

#### Confd

The Minio setting is managed by Confd. So you can custom it:
- **CONFD_BACKEND**: The Confd backend that you should use. Default is `env`.
- **CONFD_NODES**: The array of Confd URL to contact the backend. No default value.
- **CONFD_PREFIX_KEY**: The Confd prefix key. Default is `/gocd`


#### GoCD Server

The following parameters permit to config GoCD server:
- **GOCD_CONFIG_work-dir**: The directory where GoCD store data. Default is `/data`.
- **GOCD_CONFIG_config-dir**: The directory where GoCD store config. Default is `/data/config\`.
- **GOCD_CONFIG_log-file**: The file where GoCD logs stdout. Default is `/data/logs/gocd-server.log`.
- **GOCD_CONFIG_memory**: The max memory allowed to JVM.
- **GOCD_CONFIG_agent-key**: The key to use for auot registration by agent.

The following parameters permit to add plugins on GoCD server:
- **GOCD_PLUGIN_NAME = URL**:: It will download the plugin on `/data/plugin/external`.
