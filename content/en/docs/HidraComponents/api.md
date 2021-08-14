---
title: "API & Webapp 🌐"
linkTitle: "API & Webapp🌐"
date: 2021-08-01
weight: 2

---
If you want to monitor your services from different locations, constantly and want to store the results in a database, you will need to generate a Hidra-api. Hidra-API is the first component you will need to be able to monitor your services 24/7.

Hidra API will allow you to store pipelines in a database, visualise metrics, connect agents, tag agents and launch tests from as many places as you want.

# Getting started
To start working with the Hidra API, simply run hidra with the `-api` argument, i.e:

    hidra -api

When you start Hidra for the first time, you will receive a root password. Store it, you will need it to perform operations. If you want to use an external database, please read [arguments](/docs/hidracomponents/arguments/#arguments-in-api-mode)

# UI
When you run Hidra API you will be able to access a webapp to configure scenarios and agents. This webapp is accessible directly from the endpoint that raises the API mode. For example, if you run `hidra -api` you will be able to access this webapp at `http://localhost:8080`.