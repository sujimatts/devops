
### VPC Endpoint
A VPC endpoint enables you to privately connect your VPC to supported AWS services and VPC endpoint services powered by PrivateLink without requiring an internet gateway, NAT device, VPN connection, or AWS Direct Connect connection. Instances in your VPC do not require public IP addresses to communicate with resources in the service. Traffic between your VPC and the other service does not leave the Amazon network.
   There are multiple types of VPC endpoints
   
    Interface - Create an interface endpoint to send traffic to endpoint services that use a Network Load Balancer to distribute traffic. Traffic destined for the                         endpoint service is resolved using DNS.

    GatewayLoadBalancer - Create a Gateway Load Balancer endpoint to send traffic to a fleet of virtual appliances using private IP addresses. You route traffic from your                           VPC to the Gateway Load Balancer endpoint using route tables. The Gateway Load Balancer distributes traffic to the virtual appliances and can                             scale with demand.

    Gateway - Create a gateway endpoint to send traffic to Amazon S3 or DynamoDB using private IP addresses. You route traffic from your VPC to the gateway endpoint using               route tables. Gateway endpoints do not enable AWS PrivateLink.


### AWS Transit Gateway
AWS Transit Gateway connects your Amazon Virtual Private Clouds (VPCs) and on-premises networks through a central hub. This simplifies your network and puts an end to complex peering relationships. It acts as a cloud router – each new connection is only made once.

### Network ACls (NACL)
A network access control list (ACL) allows or denies specific inbound or outbound traffic at the subnet level

### Security Group
AWS security group acts as a virtual firewall for your instances to control incoming and outgoing traffic. 

![image](https://user-images.githubusercontent.com/40743779/188293838-b9371fbe-7c4e-4a7a-be50-2df0a72a466a.png)

### Subnets
A subnet is a range of IP addresses in your VPC and it must reside inside an AZ
https://docs.aws.amazon.com/vpc/latest/userguide/configure-subnets.html

### Route Tables
A route table contains a set of rules, called routes, that determine where network traffic from your subnet or gateway is directed.

### VPC
https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html

### Cloudfront
cache invalidation - https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Invalidation.html

### Lambda 
AWS Lambda lets you run code without provisioning or managing servers. You pay only for the compute time you consume - there is no charge when your code is not running.
Supported List of event sourcees: https://docs.aws.amazon.com/lambda/latest/dg/lambda-services.html#intro-core-components-event-sources
