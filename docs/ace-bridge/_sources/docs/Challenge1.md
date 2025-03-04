# Challenge 1 - Ingress to Proxy

## Scenario

Let’s start the investigation to bring up back our application. The communication between the ALB inside the Ingress VPC and the Proxy VM is broken.

![Lab Overview](images/ingress-proxy.png)
_Figure 5: Ingress to Proxy Failure_

* Search for the Private IP address of the Proxy VM

```{hint}
Go to **CoPilot > Cloud Fabric > Topology** and find the Proxy VM and retrieve its IP from the **Properties** section.
```

* Try to ping the Proxy VM from the *Ingress Spoke GW*.

```{hint}
Select the *Ingress Spoke GW* on the topology and launch the **Gateway Diagnostics** for *ping/traceroute*.
```

```{attention}
By the end of this challenge you need to ensure that the flow goes beyond the Ingress spoke to the Transit and to the Proxy Spoke.
```
