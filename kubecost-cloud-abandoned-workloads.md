# Kubecost Cloud: Abandoned Workloads

{% hint style="info" %}
This documentation should only be consulted when using Kubecost Cloud! For information about the Abandoned Workloads for self-hosted Kubecost, see [here](abandoned-workloads.md).
{% endhint %}

The Abandoned Workloads page can detect workloads which have not sent or received a meaningful rate of traffic over a configurable duration.

You can access the Abandoned Workloads page by selecting _Savings_ in the left navigation, then selecting _Remedy abandoned workloads_.

The Abandoned Workloads page will display front and center an estimated savings amount per month based on a number of detected workloads considered abandoned, defined by two values:

* Traffic threshold (bytes/sec): This slider will determine a meaningful rate of traffic (bytes in and out per second) to detect activity of workloads. Only workloads below the threshold will be taken into account, therefore, as you increase the threshold, you should observe the total detected workloads increase.
* Window (days): From the main dropdown, you will be able to select the duration of time to check for activity. Presets include 2 days, 7 days, and 30 days. As you increase the duration, you should observe the total detected workloads increase.

## Filtering your abandoned workloads

Beneath your total savings value and slider scale, you will see a dashboard containing all abandoned workloads. The total number of workloads detected should appear in the top right of the table.

You can filter your workloads through four dropdowns; across clusters, namespaces, owners, and owner kinds.

Selecting an individual line item will expand the item, providing you with additional traffic data for that item.
