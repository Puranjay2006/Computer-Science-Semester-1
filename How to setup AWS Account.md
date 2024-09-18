# What is AWS?

AWS (Amazon Web Services) is a cloud platform that provides a range of services like computing power, storage, databases, and networking. It helps businesses and developers scale resources on-demand, offering pay-as-you-go pricing, without needing to own or maintain physical infrastructure.

It offers a wide range of cloud-based services, including:

1. **Computing Power** – EC2 (Elastic Compute Cloud) for running virtual servers.
2. **Storage** – S3 (Simple Storage Service) for storing large amounts of data.
3. **Databases** – RDS (Relational Database Service), DynamoDB (NoSQL), etc.
4. **Networking** – VPC (Virtual Private Cloud) to control your network environment.
5. **Machine Learning** – AI and ML services such as SageMaker for building models.
6. **Security** – IAM (Identity and Access Management) for managing user access and permissions.

# Setting up an account on AWS:

Go to: _https://aws.amazon.com/resources/create-account/_ and follow the instructions to setup an account.

# Starting an Instance in AWS:

## What is EC2 in AWS?

An EC2 instance in AWS (Amazon Elastic Compute Cloud) is a virtual server that provides resizable compute capacity in the cloud. It allows users to run applications, host websites, and process data without owning physical hardware. EC2 instances can be launched with different configurations (CPU, memory, storage) to suit various workloads, and users can scale the resources up or down as needed.

Key features of EC2 include:

- **On-demand instances**: Pay only for what you use.
- **Auto-scaling**: Automatically adjust the number of instances based on demand.
- **Customizable**: Choose operating systems, storage options, and instance types.
- **Security**: Control access with security groups and network configurations.

## Starting an EC2 Instance in AWS:

### Step 1:

On the AWS Dashboard, search for 'EC2' and click it.

### Step 2:

Scroll down and click on 'Launch Instance'.

### Step 3:

Type your server name in the 'Name and Tags' Section and choose the O.S. (Operating System) you desire. (We are choosing Ubuntu for this tutorial)

### Step 4:

In the 'Key pair (login)' section, click on 'Create new key pair'.

### Step 5:

Type your Key pair name in the 'Key pair name' Section. Select the 'RSA' Key pair type in the 'Key pair type' section. In the 'Prive key file format' section, choose '.ppk (For use with PuTTY)' from the options. Finally, click on 'Create new key pair'.

### Step 6:

In the 'Network settings' section, click on 'Allow HTTP Traffic from the internet'.

### Step 7:

Finally, in the 'Summary' section, click on 'Launch instance'.

#### After all these steps, you should have successfully setup an EC2 Instance in AWS.

# Installing PuTTY software:

## What is PuTTY software?

PuTTY is a free, open-source terminal emulator and SSH client used to remotely connect to and manage servers, typically over a network. It supports various network protocols such as SSH (Secure Shell), Telnet, and SFTP, which are commonly used for secure communications between a local machine and a remote server.

PuTTY is widely used for tasks like:
- **Connecting to remote servers** (e.g., AWS EC2 instances)
- **Transferring files securely** via SCP or SFTP
- **Managing and administering servers** through command-line access

It is especially popular among system administrators and developers for managing Linux-based servers from a Windows environment.

## How to install PuTTY software:

Go to: _https://support.bondtech.se/Guide/How%20to%20install%20PuTTY%20in%20Windows/35.html_ and follow the instructions to install the software.

## Setting up PuTTY and the Instance:

### Step 1:

Go on the Instance dashboard. You will notice that the instance is running, and below, a public IP address is visible. Copy that IP address.

If you open the IP address in your browser you'll notice nothing loads because no server is installed on your Instance as of yet. 

### Step 2:

Now Open PuTTY. You will notice a section titled "Host Name (or IP Address)". In there, paste the IP address you copied.

### Step 3:

On the left column, Click "SSH", then click "Auth", and click on "Credentials"
















