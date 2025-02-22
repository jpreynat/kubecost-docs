# Kubecost Core Architecture Overview

Below are the major components deployed with the [Kubecost Helm chart](install.md), excluding certain Enterprise components such as durable storage:

1. Kubecost Cost-Analyzer Pod
   1. Frontend: Runs Nginx and handles routing to Kubecost backend and Prometheus/Grafana
   2. Cost-model: Provides cost allocation calculations and metrics, both reads and writes to Prometheus
2. Prometheus
   1. Prometheus server: Time-series data store for cost and health metrics
   2. Kube-state-metrics (optional): Provides Kubernetes API metrics, e.g. resource requests
   3. Node-exporter (optional): Provides metrics for reserved instance recommendations, various Kubecost Grafana dashboards, and cluster health alerts
   4. Pushgateway (optional): Provides the ability for users to push new metrics to Prometheus
   5. Alertmanager (optional): Used for custom alerts
3. Network costs (optional): used for determining network egress costs. See our [Network Traffic Cost Allocation](https://docs.kubecost.com/using-kubecost/navigating-the-kubecost-ui/cost-allocation/network-allocation) doc for more information.
4. Grafana (optional): Provides supporting dashboards for Kubecost product

Today, the core Kubecost product can be run with just components 1 and 2.1. See an overview of core components in this diagram:

![Architecture Overview](/images/arch.png)

## Provider Pricing Architecture Overview

Kubecost interacts with provider pricing in a few different ways:

* onDemand Rates (AWS, Azure, GCP, and Custom Pricing CSV)
* Negotiated Rates (Azure, GCP, and Custom Pricing CSV)
* Spot Data Feed (AWS)
* [Cloud Provider Billing for Reconciliation and Out-of-Cluster Spend](cloud-integration.md)
  * [AWS Cost and Usage Report](aws-cloud-integrations.md)
  * [Azure Cost Export](azure-out-of-cluster.md)
  * [Google BigQuery Export](gcp-out-of-cluster.md)

In an Enterprise federated setup, only the Primary Kubecost Cluster needs access to the Cloud Provider Billing.

![Provider Pricing Overview](/images/cloud-bill-diagram.png)

## Enterprise Architecture Overview

The most common implementation of durable storage in the Kubecost application is with [Thanos](https://thanos.io/). Below is a high-level reference for the required components. More information on each Thanos component can be found [here](https://thanos.io/tip/components/).

![Thanos Overview](/images/thanos-architecture.png)
