# Container Request Right-Sizing

Kubecost can automatically implement its [recommendations](api-request-right-sizing-v2.md) for container [resource requests](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/#requests-and-limits) if you have the [Cluster Controller](controller.md) component enabled. Using container request right-sizing (RRS) allows you to instantly optimize resource allocation across your entire cluster, without testing complicated YAML or `kubectl` commands. You can easily eliminate resource over-allocation in your cluster, which paves the way for vast savings via cluster right-sizing and other optimizations.

## Setup

To access RRS, you must first enable the Cluster Controller. Learn more by visiting the [Cluster Controller](https://docs.kubecost.com/install-and-configure/advanced-configuration/controller) documentation. If you have a GKE/EKS/AWS Kops cluster and want full Cluster Controller functionality, you must perform the [provider service key setup](https://docs.kubecost.com/install-and-configure/advanced-configuration/controller#provider-service-key-setup). If you are using a different cluster type or do not need other Cluster Controller functionality, you can skip ahead to the [Deploying](https://docs.kubecost.com/install-and-configure/advanced-configuration/controller#deploying) section.

## Usage

Once enabled, you can follow the detailed usage guides for automatic RRS methods: "1-click" (instantaneous) and "continuous" right-sizing.

{% hint style="info" %}
Automatic container RRS is only available for your primary cluster. To use automatic RRS on a secondary cluster, you must first manually switch to that cluster via frontend. Container RRS recommendations are still supported on all configurations of Kubecost.
{% endhint %}

* [1-click](using-kubecost/navigating-the-kubecost-ui/savings/auto-request-sizing/one-click-request-sizing.md)
* [Continuous](continuous-request-sizing.md)
