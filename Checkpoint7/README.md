# Checkpoint 7 Submission

- **COURSE INFORMATION: NDD**
- **STUDENT’S NAME: Kinod Lakdinu Melewa Thanthrige**
- **STUDENT'S NUMBER: 130349210**
- **GITHUB USER_ID: 130349210-myseneca**
- **TEACHER’S NAME: Atoosa Nasiri**

### Table of Contents
1. [Part A - Creating & Configuring VMs Using Portal](#Creating-&-Configuring-VMs-Using-Portal)
2. [Part B - Basic Connectivity VM Configuration](#Basic-Connectivity-VM-Configuration)
3. [Part C - Enable IP_Forwarding Using Portal](#Enable-IP_Forwarding-Using-Portal)
4. [Part D - Creating & Configuring VM Images Using Portal](#Creating-&-Configuring-VM-Images-Using-Portal)
5. [Part E - Azure Cost Analysis Charts](#Azure-Cost-Analysis-Charts)
6. [Part F - Create Customized Azure Dashboard](#Create-Customized-Azure-Dashboard)

#

### **Creating & Configuring VMs Using Portal**

- **What is the difference between Windows machine NSG and Linux machine NSG rules? Why? Do you need a rule for ssh or rdp? What happens if you delete specific ssh and rdp rules?**

The main difference between Windows machine NSG rules and Linux machine NSG rules can be considered in the protocols and ports which are commonly associated with the specific operating systems.

For Windows machines, you typically need to allow RDP (3389) traffic if you want to connect to the Windows VM using RDP. Simply without an NSG rule allowing RDP traffic, you won't be able to establish an RDP connection. On the other hand, Linux machines usually need to allow SSH (22) traffic if you want to connect to the Linux VM using SSH. Simply without an NSG rule allowing SSH traffic, you won't be able to establish an SSH connection.

If the user deletes the specific SSH or RDP rule from the NSG which is associated with the specific virtual machine, the corresponding protocol (SSH or RDP) will be blocked. As a result, the user won't be able to establish SSH or RDP connections to the specific VM.


- **List of all Resource Groups**
<img src="Images/Resource Group List.png" alt="Resource Group List" title="Resource Group List">

- **List of all the Virtual Machines**
<img src="Images/VM List.png" alt="Virtual Machine List" title="Virtual Machine List">

- **List of all the Network NICs**
<img src="Images/Network NIC List.png" alt="NIC List" title="NIC List">

- **List of all the Network NSGs**
<img src="Images/Network NSG List.png" alt="NSG List" title="NSG List">

- **List of all the Disks**
<img src="Images/Disk List.png" alt="Disk List" title="Disk List">

#

### **Basic Connectivity VM Configuration**

#

### **Enable IP_Forwarding Using Portal**

#

### **Creating & Configuring VM Images Using Portal**

#

### **Azure Cost Analysis Charts**

#

### **Create Customized Azure Dashboard**