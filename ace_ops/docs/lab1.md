# Lab 1 - Network Domains

## 1. SCENARIO

Infrastructure <ins>was segmented</ins> recently into 2 network domains: **BU1** & **BU2**.

You are requested to ascertain the segregation between the two network domains.
![Lab Overview](images/lab1-segmentation.png)
_Figure 2: Segmentation_


## 2. VALIDATION REQUEST

* Go to **CoPilot > Settings > Resources > Task Server**
* Ensure that both **Fetch GW Routes** and **Fetch VPC Routes** intervals are set to <ins>“1 second”</ins> each and then click on **SAVE**.


![Lab Overview](images/lab1-task.png)
_Figure 2: Task Server_

![Lab Overview](images/lab1-fetchgwroutes.png)
_Figure 3: GW Routes_

![Lab Overview](images/lab1-fetchvpcroutes.png)
_Figure 4: VPC Routes_

Afterwards, click on **Commit**.
![Lab Overview](images/lab1-commit.png)
_Figure 5: Commit_

> **Note:**
>These are very aggressive settings. In a Production environment, you should not set these intervals that frequently!


- Verify connectivity between clients **within** the same BU:
    - SSH to the BU1 Frontend in AWS.
    - From BU1 Frontend ping BU1 Analytics in GCP.

There are two methods for SSH to any instances inside the multicloud infrastructure of this lab:

1. Using an **SSH client** from your laptop (<ins>recommended method!</ins>).

![Lab Overview](images/lab1-publicip.png)
_Figure 6: Public IP_

![Lab Overview](images/lab1-publicname.png)
_Figure 7: DNS name_

2. Using the **Apache Jumpbox** from the POD Portal, <ins>if you are within your corporate network and an inbound restriction is applied on port **22**</ins>.

![Lab Overview](images/lab1-jumpbox.png)
_Figure 8: Jumpbox_

![Lab Overview](images/lab1-guacamoleaccess.png)
_Figure 9: Apache Guacamole Portal_

> **HINT:**
>Please bear in mind that if you decide to use the Jumpbox, *Copy and Paste* does not work directly from the host machine, therefore activate the **Guacamole menu**, that is a sidebar which is hidden until explicitly shown. On a desktop or other device which has a hardware keyboard, you can show this menu by pressing **Ctrl+Alt+Shift** on Windows machine (**Control+Shift+Command** on Mac).

![Lab Overview](images/lab1-guacamoleterminal.png)
_Figure 10: Guacamole Menu_

> **HINT:**
>The IP addresses can be easily retrieved either from the **Properties** section of each Virtual Machine on the Topology, or alternatively, you can retrieve the **DNS symbolic name** from your personal POD portal.

![Lab Overview](images/lab1-ec2.png)
_Figure 11: Instance Properties_