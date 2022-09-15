---
title: "Specs"
description: ""
featured_image: '/images/opi_logos/backgrounds/OPI_logo_social_dark.png'
menu:
  main:
    weight: 1
---

## OPI adopted RFC 8572 ["Secure Zero Touch Provisioning (SZTP)"](https://www.rfc-editor.org/rfc/pdfrfc/rfc8572.txt.pdf) for DPUs and IPUs

* Classic ZTP doesn't provide enough security that customers seek nowadays
* The first part of security considerations, "DPU/IPU Validation" is done using ["IEEE 802.1AR - Secure Device Identity"](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8423794)
* The second part of security considerations, "Network Validation" is done using ["A Voucher Artifact for Bootstrapping Protocols"](https://www.rfc-editor.org/rfc/pdfrfc/rfc8366.txt.pdf)
* The last step is "Artifacts Validation", download and installation (OS, config, pre and post scripts)
* The discovery is recommended but not limited to DHCP (both ipv4 and ipv6) and SLAAC (ipv6)
* The monitoring of the entire process step by step is describe in the RFC in much details
* check more info with detailed diagrams <https://github.com/opiproject/opi-prov-life/blob/main/ZTP.md>

## OPI adopted [OTEL](https://opentelemetry.io/) for DPUs and IPUs

* all vendors can implement (both linux and non-linux based)
* customers can integrate only once in their existing monitoring systems and tools
* OpenTemetry supports those data sources (Traces, Metrics and Logs)
* OPI is only mandating OTEL Specification [link](https://github.com/open-telemetry/opentelemetry-specification)
  * OTEL SDK and OTEL Collector specific implementation are left to the vendors
* OTEL Recommendation (reference):
  * micro-aggregator inside each DPU/IPU
  * macro-aggregator across DPUs and IPUs
* Next steps
  * Standardize the common metrics across DPU and IPU vendors
