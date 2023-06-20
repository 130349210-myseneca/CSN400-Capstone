# Checkpoint 6 Submission

- **COURSE INFORMATION: NDD**
- **STUDENT’S NAME: Kinod Lakdinu Melewa Thanthrige**
- **STUDENT'S NUMBER: 130349210**
- **GITHUB USER_ID: 130349210-myseneca**
- **TEACHER’S NAME: Atoosa Nasiri**

### Table of Contents

1. [Part A - Creating Network Resources using Azure CLI](#header1)
2. [Part B -  Working with Azure CLI Bash](#header2)
3. [Part C - Network Review Questions](#header3)
4. [Part D - Creating Virtual Machines](#header4)

#
### **Part A - Creating Network Resources using Azure CLI**

- **Output of the Network Configuration test file "network_config_test.sh"**
<img src="Network Config Test.png" alt="Network Config Test" title="Network Config Test">

#### **Questions:** ####
- **In network_config_test.sh what does if [[ ! $(az group list -o tsv --query "[?name=='$RG_NAME']") ]] do? Explain your answer.**

It checks if a resource group with the specified name does or doesn't exist and if the condition is true (Doesn't Exsist) the code inside the if block will be executed.

- **Why is it crucial to check if a resource exist before creating it? What bash syntax do you use to test this? How do you check if a vnet exits in vnet_create.sh?**

It is crucial to check if a resource exists before creating it to avoid conflicts and errors. "-z" operator can be used to test if a variable is empty.

- **What is the Azure CLI command to create vnet? Give the specific command as per your environment and unique ID configuration. What are the required and what are the optional parameters that you need to pass to it?**

az network vnet create --name "Router-115" --resource-group "Student-RG-954296" --location "canadacentral" --address-prefix "192.168.115.0/24" --subnet-name "SN1" --subnet-prefix " 192.168.115.32/27"

"--tags", "--dns-servers" can be copnsidered as optional parameters need to pass to it


- **What is the Azure CLI command to create subnet? Give the specific command as per your environment and unique ID configuration. What are the required and what are the optional parameters that you need to pass to it?**

az network vnet subnet create --name "SN2" --resource-group "Student-RG-954296" --vnet-name "Router-115" --address-prefixes "192.168.XX.64/27"

"--nat-gateway", "--route-table" can be copnsidered as optional parameters need to pass to it
#
### **Part B -  Working with Azure CLI Bash**
- **List all VNETs using az network vnet list command and send the output in json format to vnet_list.jsonfile**

[Link to the vnet_list.json file](https://github.com/130349210-myseneca/CSN400-Capstone/blob/main/Checkpoint6/Output%20Files/vnet_list.json)

- **Get the details of your default student vnet using az show command and send the output in json format to student_vnet.json file**

[Link to the student_vnet.json file](https://github.com/130349210-myseneca/CSN400-Capstone/blob/main/Checkpoint6/Output%20Files/student_vnet.json)

- **List all peerings using az network vnet peering list command and send the output in table format to peerings.tbl file**

[Link to the peerings.tbl file](https://github.com/130349210-myseneca/CSN400-Capstone/blob/main/Checkpoint6/Output%20Files/peerings.tbl)

- **Get the details of your Router-XX subnet SN1 using az show command in json format and query it for details of subnet and rout associations. Only submit the specific property you are asked for. You will need to embed this in your README.md as per instructions.**

az network vnet subnet show -g "Student-RG-954296" -n "SN1" --vnet-name "Router-115" --query "[id]"

[
  "/subscriptions/71d310bf-1718-4d11-87d1-99a7d4e2053f/resourceGroups/Student-RG-954296/providers/Microsoft.Network/virtualNetworks/Router-115/subnets/SN1"
]


az network vnet subnet show -g "Student-RG-954296" -n "SN1" --vnet-name "Router-115" --query "[routeassociations]"

[
  null
]

- **List all routes in RT-xx using az network route-table route list command and send the output in table format to route_list.tbl file**

[Link to the route_list.tbl file](https://github.com/130349210-myseneca/CSN400-Capstone/blob/main/Checkpoint6/Output%20Files/route_list.tbl)

- **Get the details of route between your Router-xx SN1 and Server-xx SN using az network route-table route show and send the output in json format to route_details.json**

[Link to the route_details.json](https://github.com/130349210-myseneca/CSN400-Capstone/blob/main/Checkpoint6/Output%20Files/route_details.json)


- **What CLI command will show you which subnet is associated to which route in route table? (Hint: maybe start with 'az network vnet subnet show`)**

az network vnet subnet show --ids <subnet_id> --query 'routeTable.id'
#

### **Part C - Network Review Questions**
- **What is Azure Virtual Network (VNET)? Elaborate in your own words, you may use diagrams if drawn by yourself.**

Azure Virtual Network could be demonstrated as a network infrastructure in Azure that allows the user to create and manage private networks for his or her Azure resources. It offers the user with many features along side it such as network isolation, private IP addressing and secure connectivity options between resources.


- **In the context of Hybrid Cloud architecture. How on-prem computers can access resources inside Azure virtual network?**

In a Hybrid Cloud architecture, on-premises computers can access resources inside an Azure Virtual Network through the use of VPN or Azure ExpressRoute.


- **What are the most important benefits of Azure Virtual Networks? Elaborate in your own words. Do not copy/paste from Azure Documentation. Itemized list of just benefit without proper elaboration will not receive any marks**

Azure virtual networks allow the user to have the ability to do private IP addressing to the created resources, ensuring both control and privacy.

Azure virtual networks ensure the user with protection isolation to all the resources, providing the maximum protection against threats.

Azure virtual networks also provides the user with secure communication  between on-premises networks and resources created inside azure which is very usefull in a bussiness environmnet

- **What is the difference between Network Security Group (NSG) and Route-Tables?**

Simply to put Network Security Groups or NSGs are a security eature that acts as a virtual firewall for controlling inbound and outbound network traffic covering all azure resources while on the other hand Route Tables control the routing of network traffic within a Virtual Network. 

- **What is the difference between NSG and Firewalls?**

As mentioned above NSG or Network Security Groups focus on traffic filtering and enforcing security policies, but on this case Firewalls way more advanced than NSGs and they operate at the application level (7th layer) and therefore provides advanced application level filtering and additional features for comprehensive network security management.

- **What is a hob-and-spoc network topology and how be deployed in Azure Cloud?**

A hob-and-spoc network topology is a networking architecture where a central "hub" network connects to multiple "spoke" networks. In Azure, the user can deploy it using Virtual Networks  and Virtual Network Peering.

- **In working with Azure VNETs, do you need o to define gateways for Azure to route traffic between subnets?**

No, you do not need to define gateways in Azure VNETs to route traffic between subnets within the same VNET.


- **When do you need to configure and use Virtual Network Gateways?**

Usually you need to configure and use Virtual Network Gateways in Azure when you want to establish connectivity between Azure VNETs and on-premises networks or between Azure VNETs in different regions.

#

### **Part D - Creating Virtual Machines**
- **Virtual Machines: **
<img src="Virtual Machines.png" alt="Virtual Machines" title="Virtual Machines">

#### **Questions:** ####

- **List all VMs and send the output in table format to vm_list.tbl file. What command did you use?**

az vm list --output table >> vm_list.tbl

[Link to the vm_list.tbl file](https://github.com/130349210-myseneca/CSN400-Capstone/blob/main/Checkpoint6/Output%20Files/vm_list.tbl)


- **Get the details of your WC-99 using az show command and send the output in json format to WC-99-details.json file. What command did you use?**

az vm show --name WC-115 --resource-group Student-RG-954296 --output json >> WC-99-details.json

[Link to the WC-99-details.json file](https://github.com/130349210-myseneca/CSN400-Capstone/blob/main/Checkpoint6/Output%20Files/WC-99-details.json)

- **List all NSG using az list command and send the output in table format to nsg_list.tblfile. What command did you use?**

az network nsg list --output table >> nsg_list.tbl

[Link to the nsg_list.tbl file ](https://github.com/130349210-myseneca/CSN400-Capstone/blob/main/Checkpoint6/Output%20Files/nsg_list.tbl)

- **After deleting list all your VMs using az  vm list ... with the output in table format. What command did you use? How can you ensure all your VMs are deleted?**

az vm list --output table 

As there were no output from the command we can ensure that all the virtual machines have been deleted. Additionally, we can also check the resource group for more confirmation.

- **Provide screenshot of auto shutdown configuration for LS_XX. Is there any command to show this? What is the time-zone? What should be the correct time settings considering the time zone differences?**

<img src="Auto Shutdown.png" alt="Auto Shutdown" title="Auto Shutdown">

az vm get-boot-diagnostics-data --resource-group "Student-RG-954296" --name "LS-115" --output json

Correct time zone should be Pacific Time (US and Canada) and we also need to change the Scheduled shutdown time accordingly. 

- **ALL THE VIRTUAL MACHINES ARE SUCESSFULLY DELETED**
<img src="All VMS Deleted.png" alt="All VMS Deleted" title="All VMS Deleted">

#










