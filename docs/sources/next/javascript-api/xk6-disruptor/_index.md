---
title: xk6-disruptor API
excerpt: 'An overview of the API for xk6-disruptor.'
weight: 14
---

# xk6-disruptor API

The xk6-disruptor API is organized around _disruptors_ that affect specific targets such as pods or services. These disruptors can inject different types of [faults](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/xk6-disruptor/faults) on their targets.

| Class                                                                                                      | Description                                                      |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| [PodDisruptor](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/xk6-disruptor/poddisruptor)         | Targets the Pods that match selection attributes such as labels. |
| [ServiceDisruptor](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/xk6-disruptor/servicedisruptor) | Targets the Pods that back a Kubernetes Service                  |
