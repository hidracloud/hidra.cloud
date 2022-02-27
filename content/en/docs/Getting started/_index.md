---
title: "Getting Started"
linkTitle: "Getting Started"
weight: 2
description: >
  What does your user need to know to try your project?
---

## Installation 💾
Hidra can be downloaded as binaries for any operating system, or using the Docker image. In the official Github repository you can see all available releases. To download the latest version available, you can access here: https://github.com/hidracloud/hidra/releases/latest

For example, if you want to download version 2.1.1 for Linux (64 bits):
1. `wget https://github.com/hidracloud/hidra/releases/download/v2.1.1/hidra-v2.1.1-linux-amd64.tar.gz`
2. `tar -xvf hidra-1.0.0-linux-amd64.tar.gz`
3. `sudo cp hidra-*/hidra /usr/local/bin/hidra`

In the other hand, if you want to try Docker image just use the following image: `docker pull ghcr.io/hidracloud/hidra:v1.0.0`

## Try it out! 🧸

Hidra contains a test mode, which allows you to run test pipelines directly. In the Github repository you can find examples of the different scenarios, if you want to test for example Hidra with the HTTP example, you can do the following:
1. Download example scenario: `wget https://raw.githubusercontent.com/hidracloud/hidra/main/examples/http_test.yaml`
2. Run: `hidra -test -file http_test.yaml`

Edit the http_test.yaml file to your liking and start getting familiar! 🧑‍🍳