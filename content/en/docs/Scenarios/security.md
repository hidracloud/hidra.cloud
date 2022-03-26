---
title: "Security"
linkTitle: "Security"
date: 2022-04-01
weight: 1
---
# Steps

## portScanner

| Param | Description    | Optional |
|:----------|:-------------|:-------------|
| hostname      |  Where you want to run port scanner?  | No |
| protocol     |  Which protocol do you want to use? (tcp/udp) | Yes |
| port_start    |  Which port do you want to start from? | Yes |
| port_end      |  Which port do you want to end at? | Yes |
| fingerprint | If you want to detect by fingerprint too | Yes |
| workers | How many workers do you want to use? | Yes |

## subnetPortScanner

| Param | Description    | Optional |
|:----------|:-------------|:-------------|
| cidr      |  Where you want to run port scanner?  | No |
| protocol     |  Which protocol do you want to use? (tcp/udp) | Yes |
| port_start    |  Which port do you want to start from? | Yes |
| port_end      |  Which port do you want to end at? | Yes |
| fingerprint | If you want to detect by fingerprint too | Yes |
| workers | How many workers do you want to use? | Yes |

# Example

```yaml
name: security_basic_example
description: Test that scanme.nmap.org is reachable from the internet
scrapeInterval: 1m
timeout: 1s
scenario:
  kind: security
  steps:
    - type: subnetPortScanner
      timeout: 1h
      params:
        cidr: 10.18.3.1/24
```
