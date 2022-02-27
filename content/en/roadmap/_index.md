
---
title: "🚶‍♂️ Roadmap"
linkTitle: "🚶‍♂️ Roadmap"
weight: 15
menu:
  main:
    weight: 15
---

{{< blocks/cover title="Roadmap" image_anchor="bottom" height="min" >}}
<p class="lead mt-5">What is the way forward?
</p>

{{< /blocks/cover >}}

{{< blocks/section >}}

<div class="col-6">
  <h1 class="text-center">Short term</h1>
  <ul>
    <li>
      Add prometheus configuration, hidra already generate Prometheus metrics
    </li>
    <li>
      Add prometheus alerting examples
    </li>
    <li>
      Add example grafana dashboards
    </li>
    <li>
      Add more scenario examples
    </li>
    <li>
      Generate a *.deb package for every release
    </li>
    <li>
      Add an example of how to use hidra for functional tests
    </li>
    <li>
      Improve documentation
    </li>

  </ul>
</div>
<div class="col-6">
  <h1 class="text-center">Long term</h1>
  <ul>
    <li>
      Add Hidra-exporter operator for an easy way to deploy Hidra on Kubernetes
    </li>
    <li>
      Add load testing mode for Hidra
    </li>
    <li>
      Create a new software piece that will receive alertmanager alerts, and Hidra RCA from failing scenarios.
    </li>
  </ul>

</div>

{{< /blocks/section >}}