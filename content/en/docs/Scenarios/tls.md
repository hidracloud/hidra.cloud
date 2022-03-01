---
title: "TLS"
linkTitle: "TLS"
date: 2021-08-01
weight: 1
---
# Steps

## connectTo
| Param | Description    |
|:----------|:-------------|
| to      | Which host:port do you want to request?  |

## dnsShouldBePresent
| Param | Description    |
|:----------|:-------------|
| dns      | Check if DNS is present on certificate  |

## shouldBeValidFor
| Param | Description    |
|:----------|:-------------|
| for      | Check that it is valid for a period of time. Valid values could be: 15m, 1h, 1d... |

## dumpMetrics
| Param | Description    |
|:----------|:-------------|

# Example

```yaml
name: tls_basic_example
description: Test that google.com has a TLS certificate
scrapeInterval: 1m
scenario:
  kind: tls
  steps:
    - type: connectTo
      params:
        to: google.com:443
    - type: dnsShouldBePresent
      params:
        dns: google.com
    - type: shouldBeValidFor
      params:
        for: 7d
    - type: dumpMetrics
```