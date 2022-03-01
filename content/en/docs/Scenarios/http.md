---
title: "HTTP"
linkTitle: "HTTP"
date: 2021-08-01
weight: 1
---
# Steps

## request
| Param | Description    |
|:----------|:-------------|
| url      | Which url do you want to request?  |
| method    | Which HTTP method do you want to use?  | 

## statusCodeShouldBe
| Param | Description    |
|:----------|:-------------|
| statusCode      | Check status code from request  |

## bodyShouldContain
| Param | Description    |
|:----------|:-------------|
| search      | Which term do you want to search for? |

## shouldRedirectTo
| Param | Description    |
|:----------|:-------------|
| url      | Which is the new location?  |

# Example
```yaml
name: http_basic_example
description: Test that example.com return HTTP 200
scrapeInterval: 1s
timeout: 1s
tags:
  sla: dev
scenario:
  kind: http
  steps:
    - type: addHTTPHeader
      params:
        key: Hidra-Token
        value: asd
    - type: request
      params:
        url: "https://example.org/?{{ .Now.Unix }}"
    - type: statusCodeShouldBe
      params:
        statusCode: "200"
    - type: bodyShouldContain
      params:
        search: example
    - type: bodyShouldContain
      params:
        search: aebfou3rfbro3b3oon
      negate: true
```