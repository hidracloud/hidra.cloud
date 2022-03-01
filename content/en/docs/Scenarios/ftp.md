---
title: "FTP"
linkTitle: "FTP"
date: 2021-08-01
weight: 1
---
# Steps

## connectTo
| Param | Description    |
|:----------|:-------------|
| to      | Which host:port do you want to request?  |

## login
| Param | Description    |
|:----------|:-------------|
| user | Username to use for login  |
| password | Password to use for login  |

## write
| Param | Description    |
|:----------|:-------------|
| test-file | File to write  |
| data | Data to write  |

## read
| Param | Description    |
|:----------|:-------------|
| test-file | File to read  |
| data | Data to read  |

## delete
| Param | Description    |
|:----------|:-------------|
| test-file | File to delete  |

# Example
```yaml
name: ftp_basic_example
description: Test that google.com has a TLS certificate
scrapeInterval: 1m
scenario:
  kind: ftp
  steps:
    - type: connectTo
      params:
        to: ftp.dlptest.com:21
    - type: login
      params:
        user: dlpuser
        password: rNrKYTX9g7z3RgJRmxWuGHbeu
    - type: write
      params:
        data: "test"
        test-file: test-file.txt
    - type: read
      params:
        test-file: test-file.txt
        data: "test"
    - type: delete
      params:
        test-file: test-file.txt
```