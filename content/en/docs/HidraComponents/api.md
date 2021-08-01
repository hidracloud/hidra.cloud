---
title: "API 🌐"
linkTitle: "API"
date: 2021-08-01
weight: 2

---
If you want to monitor your services from different locations, constantly and want to store the results in a database, you will need to generate a Hidra-api. Hidra-API is the first component you will need to be able to monitor your services 24/7.

Hidra API will allow you to store pipelines in a database, visualise metrics, connect agents, tag agents and launch tests from as many places as you want.

# Getting started
At the moment, Hidra only supports SQLite databases, support for other databases will come in the next release, currently, Hidra-API and Hidra-Agent are proof of concepts.

To start working with the Hidra API, simply run hidra with the `-api` argument, i.e:

    hidra -api

When you start Hidra for the first time, you will receive a root password. Store it, you will need it to perform operations.

# API Methods

## [GET] Ping: `/ping`
It will return Pong: true if everything is OK.


## [POST] Login: `/login`
As the name suggests, it allows us to log in. It will return a LoginToken that you can use to authenticate your requests. You should send this token as `Bearer token`

    {
        "Email": "root",
        "Password": "your-root-password"
    }


## [GET] Ping: `/agent_token`
Generate a pre-register agent token.

## [POST] Login: `/register_sample`
It will allow you to register new samples to be read by the agents.

    name: http_basic_example
    scrapeInterval: 1m
    scenarios:
    - name: http_test_example
        description: Test that example.com return HTTP 200
        kind: http
        steps:
        - type: request
            params:
            url: 'https://example.org/'
        - type: statusCodeShouldBe
            params:
            statusCode: '200'
        - type: bodyShouldContain
            params:
            search: example
        - type: bodyShouldContain
            params:
            search: aebfou3rfbro3b3oon
            negate: true
