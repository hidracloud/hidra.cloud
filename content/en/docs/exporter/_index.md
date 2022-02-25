---
title: "Exporter"
linkTitle: "Exporter"
date: 2021-08-01
weight: 6
---
If you want to run Hidra in exporter mode, you can use the following command:

    hidra -exporter -conf /path/to/all/samples

Where `/path/to/all/samples` is the path to all samples, you can use subfolders to organize your samples, for example, you can deploy all your samples on `/etc/hidra/samples`, and inside this folder, you can have a folder for each client, for example, `/etc/hidra/samples/client1`, `/etc/hidra/samples/client1`, etc.

Then, after running Hidra on exporter mode, you can add its as target to your Prometheus configuration.