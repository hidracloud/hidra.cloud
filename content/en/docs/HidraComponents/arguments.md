---
title: "Arguments"
linkTitle: "Arguments"
date: 2021-08-01
weight: 4
---
You can configure Hidra through arguments or through environment variables. Here, we will explain each of the arguments that Hidra accepts. If you want to make it an environment variable, simply capitalise the argument.

## Setting the operating mode
You can combine these flags as you like, for example, if you call hidra with the -api and -metric flags, Hidra will be working as an API and as a metrics endpoint for Prometheus.

| Argument | Description    | Value type | Default |
|:----------|:-------------|:------------| -------- |
| api      | Activate API mode in Hidra. | bool | false |
| agent    | Activate agent mode in Hidra. | bool | false |
| test     | Activate test mode in Hidra. | bool | false |
| metric     | Activate metric mode in Hidra. | bool | false |

## Arguments in test mode
| Argument | Description    | Value type | Default |
|:----------|:-------------|:------------|---------|
| file      | Yaml file that will run Hidra in test mode. | string | |

## Arguments in API mode
| Argument | Description   | Value type | Default |
|:----------|:-------------|:------------|--------|
| listen_addr  | Listen address for API endpoint. | string | :8080 |
| db_type  | Specifies the type of database to be used by Hidra. Allowed values are: *sqlite, mysql, postgresql*. | string | sqlite |
| db_path  | Only required if you're using sqlite. Specify sqlite db file. | string | test.db |
| db_uri  | Specifies the connection URL of the database in DSN format. | string |  |

## Arguments in metric mode
| Argument | Description   | Value type | Default |
|:----------|:-------------|:------------|--------|
| metric_listen_addr  | Listen address for Metric endpoint. | string | :9096 |
| metric_pull_seconds  | How long should it take between each Prometheus metrics update? | int | 1 |

## Arguments in agent mode
| Argument | Description   | Value type | Default |
|:----------|:-------------|:------------|--------|
| agent_secret  | Token for agent authentication | string |  |
| api_url  | URL of your API | string | http://localhost:8080/api |
| data_dir  | Path where agent will store data | string | /var/tmp/agent-data |
