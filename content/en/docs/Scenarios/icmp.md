---
title: "ICMP"
linkTitle: "ICMP"
date: 2021-08-01
weight: 1
---
# Steps

## ping
| Param | Description    | default |
|:----------|:-------------|:-------------|
| hostname      | Where do you want to ping?  | |
| times  *(optional)*  | How many times do you want to ping | 3 |

### Custom metrics
| Metric | Description    | 
|:----------|:-------------|
| packet_loss      | number of lost packets  |
| min_rtt      | min ping |
| max_rtt      | max ping |
| avg_rtt      | avg ping |
| packet_duplicates | duplicate packets |
| packet_receive | packets received |
| packet_send | packets send |

## traceroute
| Param | Description    | default |
|:----------|:-------------|:-------------|
| hostname      | Where do you want to ping?  | |

### Custom metrics
| Metric | Description    | 
|:----------|:-------------|
| hop_%d_elapsed      | time to completed hop |
| hop_%d_status     | hop status |
| hops      | number of hops |

# Example
```yaml
name: icmp_test_ping
description: Test ping to 8.8.8.8
scrapeInterval: 1m
scenario:
  kind: icmp
  steps:
    - type: ping
      params:
        hostname: 8.8.8.8
        times: 3
```

```yaml
name: icmp_test_ping
description: Test traceroute to 8.8.8.8
scrapeInterval: 1m
scenario:
  kind: icmp
  steps:
    - type: traceroute
      params:
        hostname: 8.8.8.8
```