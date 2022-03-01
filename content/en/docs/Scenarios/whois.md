---
title: "Whois"
linkTitle: "Whois"
date: 2021-08-01
weight: 1
---
Introduced in v2.1.0
# Steps

## whoisFrom
| Param | Description    |
|:----------|:-------------|
| domain      | Which host:port do you want to request?  |

## shouldBeValidFor
| Param | Description    |
|:----------|:-------------|
| for      | Duration to check |
| dateFormat | Format of the date |

## dumpMetrics
| Param | Description    |
|:----------|:-------------|

# Example
```yaml
name: whois_basic_example
description: Test that google.com dns are ok
scrapeInterval: 1s
timeout: 1s
tags:
  sla: dev
scenario:
  kind: whois
  steps:
    - type: whoisFrom
      params:
        domain: google.com
    - type: shouldBeValidFor
      params:
        period: 1d
```