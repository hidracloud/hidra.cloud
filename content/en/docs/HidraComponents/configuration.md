---
title: "Configuration"
linkTitle: "Configuration"
date: 2021-08-01
weight: 4
---
You can configure Hidra through arguments or through environment variables. Here, we will explain each of the arguments that Hidra accepts. If you want to make it an environment variable, simply capitalise the argument.

## Setting the operating mode
You can combine these flags as you like, for example, if you call hidra with the -api and -metric flags, Hidra will be working as an API and as a metrics endpoint for Prometheus.

| Argument | Description    | Value type | Default |
|:----------|:-------------|:------------| -------- |
| exporter      | Activate exporter mode in Hidra. | bool | false |
| test     | Activate test mode in Hidra. | bool | false |

## Arguments in test mode
| Argument | Description    | Value type | Default |
|:----------|:-------------|:------------|---------|
| file      | Yaml file that will run Hidra in test mode. | string | |

## Arguments in exporter mode
| Argument | Description    | Value type | Default |
|:----------|:-------------|:------------|---------|
| maxExecutor      | How many executors will run in parallel | int | |
| port      | Port to expose metrics. | int | |
| buckets     | Buckets for histogram. | int | |
| conf | Path to all samples. | string | |