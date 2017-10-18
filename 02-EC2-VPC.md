## Gettign Inside the Virtual Machine with EC2 and VPC

### VPC (Virtual Private Cloud)
Adds layer of security separating your resources from the others.
- Resources get private IP addresses.
- Free service (maximum 5/account)

Key structures:
1. Security groups: collection of Ips that are allowed to connect to and from your instance. You can add policies to allow connections between different security groups.
2. Routing tables: configure routing destinations.
3. Network Access Control List: sets wich IPS are allowed to access the VPC.
4. Subnets: instances must be launched within a Subnet. Each VPC must have at least on Subnet and one subnet has it's own routing table and Network Access Control List. You could setup a private subnet and a public subnet in the same VPC.

#### Creating a Virtual Private Cloud
Simple VPC with 2 Subnets.
- Create a VPC from the Services menu (includes creation of a Subnet)
- Go to the Route Table for the PVC created, create a new route with Destination 0.0.0.0/0 this creates a route to let outgoing traffic get to the outside world.
- Create Subnet with different IPV4, if first one was 10.0.0.0/24 new one will be 10.0.1.0/24 so we get another 255 IP addresses.

### EC2 (Elastic Cloud Compute)
Virtual machine service that runs software of your choice.
AMI: operatinc system + software installed on EC2 marketplace.

#### Creating an EC2 instance
Follow the wizard, adding settings so the instance can be accessed through http on the correct port.
