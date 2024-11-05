# Virtual Networking

* A technology emulating physical network infrastructure within a software-defined environment, such as routers, switches, and firewalls.
* Enables the creation of isolated, secure, and scalable networks.
* Offers flexibility in network configuration and management.
* Often used in cloud computing environments to provide virtualized network services to multiple tenants.

## VPC (Virtual Private Cloud)

* A logically isolated section of the AWS cloud where you can launch AWS resources.
* Acts as a private data center within the AWS cloud.
* Provides granular control over network configuration, including IP address ranges, routing tables, and security groups.
* Can be used to create highly available and fault-tolerant applications.

## Subnets

* Divisions within a VPC that define ranges of IP addresses.
* Used to organize resources logically and control access.
* Can be public or private:
    * **Public subnets:** Connected to the internet gateway, allowing instances to communicate directly with the internet.
    * **Private subnets:** They are not directly connected to the internet, but they provide enhanced security.

## Route Tables

* Contain rules that determine how traffic is routed within a VPC.
* Each subnet is associated with one or more route tables.
* Route table rules specify the destination IP address range and the target gateway or instance.
* Used to implement network security policies, such as routing traffic to specific instances or preventing access to certain resources.

## Internet Gateway

* A gateway that enables instances in public subnets to communicate with the internet.
* Acts as a bridge between the VPC and the public internet.
* Essential for internet-facing applications and services, such as web servers and APIs.

## Virtual Private Gateway

* A gateway that enables secure, encrypted communication between your VPC and your on-premises network.
* Creates a site-to-site VPN connection.
* Used to extend your on-premises network into the AWS cloud, enabling hybrid IT environments.

## Elastic Load Balancer

* Distributes incoming traffic across multiple instances to improve performance, reliability, and scalability.
* Offers different types of load balancers for various use cases:
    * **Application Load Balancer:** Distributes traffic based on application layer protocols (HTTP, HTTPS).
    * **Network Load Balancer:** Distributes traffic at the transport layer (TCP, UDP).
    * **Classic Load Balancer:** Legacy load balancer, primarily used for EC2 instances.
* Provides features like health checks, automatic scaling, and SSL termination.

## Steps to create a Load Balancer in AWS:

1. Create a VPC
2. Create Subnets
3. Create an Internet Gateway and attach it to VPC 
4. Create a Virtual Private Gateway and Attach it to VPC
5. Create Route Tables and attach them to Subnets
6. Create the Elastic Load Balancer (ELB)

### Step-1: Create a VPC

* To do this, first log in to your AWS Account. 
* Then, search for VPC in the AWS Dashboard. 
* After this, select the first option, 'Your VPCs'.

AWS Console -> Services -> Networking & Content Delivery -> VPC -> Your VPCs 

![image](https://github.com/user-attachments/assets/ec8902eb-4ee6-40c9-961d-0c4cc33f0777)

Now, click on 'Create VPC'

![image](https://github.com/user-attachments/assets/d7dfeae5-76b1-4199-bf8a-7f7745e38c5f)

Now, enter these details:

![image](https://github.com/user-attachments/assets/ce0e7be7-7106-4e30-830b-92cb124d9e33)

Finally, click on 'Create VPC'.

![image](https://github.com/user-attachments/assets/ba1bafa5-5d66-43db-a827-6fbee38b8855)

After creating the VPC, you should see a message that your VPC is successfully created and a page like this:

![image](https://github.com/user-attachments/assets/c4fd3595-2637-4f70-9f2d-9c739646e15b)

Now, go back to 'Your VPCs' and you should be able to see your newly created VPC, as shown below:

![image](https://github.com/user-attachments/assets/b47c6cff-8551-4625-bd0f-7b65cb78617f)

### Step-2: Create Subnets

After creating your VPC, you must create 4 Subnets, 2 of which will be private and 2 of which will be public.

To create your subnets, select the 'Subnets' option, available on the VPC Dashboard, right below 'Your VPCs':

![image](https://github.com/user-attachments/assets/971292df-a98b-49e9-9692-71722dd4c4d0)

After clicking it, a page opens with all your pre-existing subnets, which you can delete if you don't want. 

![image](https://github.com/user-attachments/assets/6ce11617-0ff7-4d60-b67f-2a5c013fbcc1)

Now, click on 'Create Subnet'

![image](https://github.com/user-attachments/assets/32501629-4c31-49f4-a59f-9a30a3ff3c67)

Now, on the page opened, select your previously created VPC from the options available in the 'VPC ID' Section: (This means that you are creating Subnets within your previously created VPC, 'MyVPC'.)

![image](https://github.com/user-attachments/assets/31ee59ac-eb7a-4867-94ad-79423065d86a)

Now, in the Subnet Settings Section, create your first Subnet with the details as shown below:

![image](https://github.com/user-attachments/assets/763e2479-78e9-4b2c-9e2a-cfd8a69fe53d)

Then, to create a new Subnet, click on the 'Add New Subnet' option as shown below:

![image](https://github.com/user-attachments/assets/7afe1afe-82e0-4a46-bea0-140416409e20)

Now, create your 2nd Subnet with the details as shown below:

![image](https://github.com/user-attachments/assets/81ab2a1a-c819-4dcc-ae62-d2d431a3841d)

Similarly, create the 3rd and 4th Subnets with the details as shown below:

![image](https://github.com/user-attachments/assets/2cd86bf5-3120-4bd9-a662-da8071b0b5b4)
![image](https://github.com/user-attachments/assets/c5534b70-20f5-4815-b97c-3b927177047b)

Finally, click on 'Create Subnet'.

Now, you should be able to see your successfully created Subnets on the dashboard, as shown below:

![image](https://github.com/user-attachments/assets/3b529278-05ab-4a76-8d7a-9be8ffd0c8c0)

You can refer to this table for more clarity on the details of each Subnet that we have created:

![image](https://github.com/user-attachments/assets/bde40905-727f-4758-aa42-7c0c75dfa20c)

### Step-3: Create an Internet Gateway and attach it to VPC

After creating Subnets, our next step is to create an internet gateway, which we will then attach to our previously created VPC, 'MyVPC'.

To do this, select the Internet Gateway option from the VPC Dashboard, right below 'Route Tables':

![image](https://github.com/user-attachments/assets/463c68fb-0e60-4725-adfd-631ad90f1332)

Then, click on 'Create Internet Gateway'. On this screen, give a name to your Internet Gateway and create it, as shown below:

![image](https://github.com/user-attachments/assets/562cb35d-2b4d-4af9-b09a-f4b0b4d09d50)

Then, click on the Actions Button and select 'Attach to VPC'.

![image](https://github.com/user-attachments/assets/d86edd70-eefa-44d3-835a-d04daa6cd7e6)

Then, on the opened screen, select you previously created VPC, 'MyVPC' from the options available in the drop-down menu, and finally, click 'Attach Internet Gateway'.

![image](https://github.com/user-attachments/assets/6edbda81-79ca-45cf-9214-ab08142a630e)

Now, your Internet Gateway is successfully attached to your VPC.

![image](https://github.com/user-attachments/assets/d308d28d-8fb3-4424-aee6-36ef4e8758c3)

You should also be able to see your newly created IGW (MyIGW) on the Dashboard.

![image](https://github.com/user-attachments/assets/2fc6c854-c8a0-4e01-be71-7012fe82875e)

### Step-4: Create a Virtual Private Gateway and Attach it to VPC

Now, after creating an Internet Gateway (IG) and attaching it to your VPC, it is time to create a Virtual Private Gateway (VPG) and attach that to your VPC as well.

Scroll down a bit on the VPC Dashboard, until you reach the Virtual Private Network VPN) Section, and in the options, click on 'Virtual Private Gateway'.

![image](https://github.com/user-attachments/assets/58021633-b063-47e1-9ee1-11dd3a14edfc)

Now, create a VPG.

![image](https://github.com/user-attachments/assets/f8bea83f-f6fa-4739-8957-4b82fb19f913)

Give a name to your VPG and then create it, as shown below

![image](https://github.com/user-attachments/assets/c6bb202e-cbc1-4fdb-bb03-0ebfd56d2aa1)

After successfully creating your VPC, you need to attach it to your VPC. 

On the dashboard, select your newly created VPG, and then from the options in the 'Actions' Button, click on 'Attach to VPC'.

![image](https://github.com/user-attachments/assets/4ef66094-5121-4945-9e0b-e93b8c320437)

Choose your VPC from the options available and, finally, click on 'Attach to VPC'.

![image](https://github.com/user-attachments/assets/f45e2e34-4525-46e9-b33c-273d49952376)

### Step-5: Create Route Tables and attach them to Subnets

After creating your VGW and attaching it to your VPC, we need to create Route Tables and attach them to Subnets.

Scroll up on the VPC Dashboard and click on 'Route Tables', within the 'Virtual Private Cloud Section'.

![image](https://github.com/user-attachments/assets/ccf347a3-8c57-4b5f-9b32-cd40dfe6dc50)

We need to create the following Routes:

One route is for the Internet gateway, other for the Virtual Private Gateway (R1-IGW and R2-VGW) 
* Route 1 (R1) - 0.0.0.0/0 to IGW 
* Route 2 (R2) - 192.168.0.0/16 to VGW

Create R1-IGW and R2-VGW with the following details as mentioned below: (Don;t forget to attach each Route Table you create with your VPC)

![image](https://github.com/user-attachments/assets/92ed99a2-c5f1-4f5e-bea1-69244ca43704)
![image](https://github.com/user-attachments/assets/c0a62ec3-2a5a-41e5-b85d-ea0d30997af3)

Now, select R1-IGW and go to the Routes Option.

![image](https://github.com/user-attachments/assets/7cafbea7-406c-42a2-9552-2f04a3216152)

There, select the 'Edit Routes' Option.

![image](https://github.com/user-attachments/assets/cc7fa42f-4a7b-47fc-8513-e8e563fce15c)

After clicking on the 'Edit Routes' Option, this page should open up:

![image](https://github.com/user-attachments/assets/5f00dbab-f4de-48a3-a79e-cb7043a08008)

Here, we have to add a Routing Rule for R1-IGW. 

To do this, click on the 'Add Route' button:

![image](https://github.com/user-attachments/assets/a754931d-c65f-4563-a9f5-b12d9e348285)

Now, enter the following details and click on 'Save Changes'.

![image](https://github.com/user-attachments/assets/9fb035fd-0c0f-4d24-95e3-d61c2707aab4)
(Here, we are basically adding a Routing Rule for Route 1 to target our previously created IGW)

Similarly, repeat the same steps for R2-VGW, but while on the 'Edit Routes' Page, choose your previously created VGW and enter the Destination Address as shown below:

![image](https://github.com/user-attachments/assets/6aa52447-6837-4967-978e-d5a265ecd523)
(Here, we are basically adding a Routing Rule for Route 2 to target our previously created VGW)

Now, we still have to attach our Route Tables to our Subnets.

To do so, refer to the following:

#### Route 1 (R1-IGW) is going to be attached to the Public Subnets (S3-Public and S4-Public), because,  public networks are required to have internet access, that is, they need an Internet Gateway to connect to the Internet.
#### &
#### Route 2 (R2-VGW) is going to be attached to the Private Subnets (S1-Private and S2-Private), because, private networks don't need to have internet access. They can work with a Virtual Private Gateway instead of an Internet Gateway.

Now, go back to your Subnets and start by attaching the S1-Private Subnet to Route 2 IGW (R2-VGW)

To do so, select the subnet (S1-Priavte) and go to the 'Route Tables' option as shown below:

![image](https://github.com/user-attachments/assets/9e291d0f-1373-4ed5-ad35-3c34a070f8a6)

When selected, click on the 'Edit Route Table Association' button:

![image](https://github.com/user-attachments/assets/942ef8b5-fe85-4cbd-8df9-0951d5636c67)

Then, on the opened page, select 'R2-VGW' from the options available in the drop-down menu:

![image](https://github.com/user-attachments/assets/fee8b8a8-a435-441a-bb9c-699282e7313e)

Then, click 'Save'.

Now, repeat this process for all the other Subnets.

![image](https://github.com/user-attachments/assets/c01c7d2c-9aa1-4be2-8d52-2ac21b4cf0e9)
* For S2-Private

![image](https://github.com/user-attachments/assets/562d9ecd-0fec-48b2-ab82-13ed038536b6)
* For S3-Public

![image](https://github.com/user-attachments/assets/636a7a93-d878-41e2-a1df-dfba1e48d7da)
* For S4-Public

Now, you can see that, for example, S2-Private has a VGW Route Association:

![image](https://github.com/user-attachments/assets/132999c4-c56e-4df0-aa59-070f1c292dd2)

And S4-Public has an IGW Route Association:

![image](https://github.com/user-attachments/assets/df42f891-e18d-45bc-9654-a8978991ab5a)

Hence, you have successfully attached your Route Tables to your Subnets.

Step-6: Create the Load Balancer:

* Launch two EC2 instances in different AZs 
* Enable Web services 
* Launch Load Balancer 
* Add both instances under the load balancer now check the traffic
