---
title: "Scenarios"
linkTitle: "Scenarios"
date: 2021-08-01
weight: 5
description: "Scenarios are a way to test your infrastructure. They are composed of steps that are executed in a specific order. They can be used to test your infrastructure, to test your application, to generate metrics of your uptime, to loadtest your application, or to test your infrastructure and your application. "
---
Hidra scenarios allow you to generate tests of different types in a very easy way, all tests are defined by simple tests using YAML. In this section, you will find the different types of tests you can do with Hidra.

## Monitoring

Each time a scenario is run, it checks that all conditions are met, if the conditions are not met it will generate a metric with error. In addition, Hidra stores the execution times of each scenario, for HTTP scenarios this is very useful. On the other hand, each step is able to generate its own metrics.

## Configuration
The Hidra scenarios accept the following parameters:
| Option | Description    | Value type | Default | Since |
|:----------|:-------------|:------------| -------- | -------- |
| name      | What name you want to give to the scenario.  | string |  | |
| description    | What description you want to give to the scenario.  | bool | false | |
| scrapeInterval     | In agent mode, how often to run the scenario. | int | 0 | |
| scenario     | The definition of the scenario | object | false | |
| tags | Tags to add to the scenario exposed as prometheus labels | map[string]string | {} | v2.1.0 |
To configure the scenario itself, you will need to configure the following:

| Option | Description    | Value type | Default | Since |
|:----------|:-------------|:------------| -------- | -------- |
| kind      | Hidra accepts different types of scenarios, you can specify them here. Check out the rest of the sections.  || string |  | |
| steps    | All the steps you have to execute this scenario. | array | [] | |

To configure the steps, each step must contain the following:

| Option | Description    | Value type | Default | Since |
|:----------|:-------------|:------------| -------- | -------- |
| type      | Step type inside scenario context  | string |  | |
| params    | Params for given step. | object | {} | |
| negate | If you want to check that step condition is not ok | bool | false | |
| timeout     | The maximum time to run the scenario | int | 0 | v2.1.0 | |

All this, in YAML format, would look like this:

    name: http_basic_example
    description: Test that example.com return HTTP 200
    scrapeInterval: 1m
    scenario:
    kind: http
    steps:
        - type: request
        params:
            url: "https://example.org/"
        - type: statusCodeShouldBe
        params:
            statusCode: "200"
