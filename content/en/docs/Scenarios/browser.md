---
title: "Browser"
linkTitle: "Browser"
date: 2021-08-01
weight: 1
---
Run test using Google Chrome.

# Steps

## navigateTo
| Param | Description    |
|:----------|:-------------|
| url      | Which url do you want to request?  |

## waitVisible
| Param | Description    |
|:----------|:-------------|
| selector      | Wait until selector is visible  |

## click
| Param | Description    |
|:----------|:-------------|
| selector      | Which element do you want to click? |

## urlShouldBe
| Param | Description    |
|:----------|:-------------|
| url      | Which final url |

## sendKeys
| Param | Description    |
|:----------|:-------------|
| selector      | Which element do you want to text? |
| keys      | Send keys to selector  |

## textShouldBe
| Param | Description    |
|:----------|:-------------|
| selector      | Where to search? |
| text      | Search for a text string  |

# Example
```yaml
name: browser_test
description: test browser
scrapeInterval: 1m
timeout: 1s
tags:
  sla: dev
scenario:
  kind: browser
  steps:
    - type: navigateTo
      timeout: 1m
      params:
        url: "https://hidra.cloud/"
    - type: waitVisible
      params:
        selector: "#td-cover-block-0 > div > div > div > div > div > div > a.btn.btn-lg.btn-primary.mr-3.mb-4"
    - type: click
      params:
        selector: "#td-cover-block-0 > div > div > div > div > div > div > a.btn.btn-lg.btn-primary.mr-3.mb-4"
    - type: urlShouldBe
      params:
        url: "https://hidra.cloud/docs/"
    - type: textShouldBe
      params:
        selector: 'body > div > div > div > main > div > div.pageinfo.pageinfo-primary > p'
        text: Welcome to the Hidra documentation!
```