# Lab 1 Build the MSP Backbone

## 1.0 - What's in the lab?

Lab time: ~45 minutes

This is an advanced scenario for Managed Service Providers (msps) that goes through onboarding Tenants, connecting to their respective locations, overlapping addresses and much more.

The initial lab topology can be found below and consists of:

- Shared Services spread across AWS & Azure with their respective Spoke Gateways
- Backbone layer spread across AWS & Azure. The PAN FWs have already been pre-built in AWS. In a subsequent lab, you will be building the same within Azure.
- 3 Separate Tenants (customers-a, b and c). Customers in tandem with the MSPs can host their applications and services within their dedicated & isolated space. Though we represent each customer with a single VPC, in reality the same design can scale to cater multiple VPCs, Regions, and Accounts. 
- Customer Locations: These represent locations outside the Public Cloud(s) that need connectivity to the applications and services within the Public Cloud(s)
- There are workloads spread across the topology running an NGINX server & proxy which will be used to test end to end connectivity.

![Lab Overview](images/lab1/ace_for_msps_lab_diagrams__initial_layer.png)
_Figure 1: Lab Overview_

## 1.1 - Initial Topology

Let's visit our topology page within Copilot by leveraging the Search bar as shown below.


![Search Bar](images/lab1/copilot_topology_search.png)
_Figure 2: Using the Search Bar_

![Initial Topology](images/lab1/copilot_initial_topology.png)_Figure 3: Initial Topology_


## 1.2 - Build the MSP Backbone
Having looked at the initial overall topology we will focusing on the Backbone area for this lab. The initial status of the backbone area is as shown here.

![Backbone Area](images/lab1/backbone_area.png)_Figure 4: Backbone Area Initial Status_

### 1.2.1 - Connect AWS Shared Svcs to AWS Hub

Navigate to the Gateways menu within Copilot by leveraging the search bar as shown below. 

![Search Bar](images/lab1/search_bar_gateways.png)_Figure 5: Search Bar to Reach Gateways_

![Select aws-shared-svcs](images/lab1/aws_shared_svcs_edit_spoke.png)_Figure 6: Select aws-shared-svcs Gateways_

![Connect AWS Shared Svcs to Backbone](images/lab1/attach_aws_shared_svcs_to_aws_hub.png)_Figure 7: Attach aws-shared-svcs to aws-hub transit gateway_

### 1.2.2 - Connect Azure Shared Svcs to Azure Hub

![Select azure-shared-svcs](images/lab1/azure_shared_svcs_edit_spoke.png)_Figure 8: Select aws-shared-svcs Gateways_

![Connect Azure Shared Svcs to Backbone](images/lab1/attach_azure_shared_svcs_to_aws_hub.png)_Figure 9: Attach azure-shared-svcs to azure-hub transit gateway_

## 1.2.3 - Configure Transit Peering between AWS & Azure

![Select AWS Transit Hub](images/lab1/choosing_aws_hub_transit.png)_Figure 10: Select AWS Hub Transit_

![Configure Peering with Azure Hub](images/lab1/peering_aws_hub_with_azure_hub_transits.png)_Figure 11: Configure Peering with Azure Hub Transit_



##  1.3 - Verification of Attachments & Peerings

![Spoke to Transit Attachment Verification](images/lab1/proof_of_attaching_aws_azure_shared_svcs_to_hub.png)_Figure 12: Spoke to Transit Attachment Verification_

![AWS & Azure Hub Peering Verification](images/lab1/proof_aws_and_azure_hub_peering_transits.png)_Figure 13: AWS & Azure Hub Peering Verification_

![Topology Verification](images/lab1/topology_proof_aws_and_azure_hub_peering_transits.png)_Figure 14: Topology Verification_

![Current Topology](images/lab1/backbone_area_configured.png)_Figure 15: Current State of the Topology_


## 1.4 Data Plane Verification

![Instance IPs](images/lab1/find_ip_address_of_machine.png)_Figure 16: Find Instance IP Address_


![Ping Verification](images/lab1/ping_from_aws_log1_to_azure_log1.png)_Figure 17: Ping Verification_

![Browser Verification](images/lab1/web_browser_to_aws_log1.png)_Figure 18: Access aws-log1 Application_

![Browser Verification](images/lab1/web_browser_to_azure_log1_through_aws_log1.png)_Figure 19: Verification Leveraging NGINX Proxy_

##  1.5 - Conclusion
In this lab, we have built our MSP backbone layer and ensured end to end connectivity across the MSP. 
