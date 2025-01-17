# Terraform AWS VPC Module Customised
This module is going to create the following resources. For HA we are going to get first 2 AZ

* VPC
* Internet Gateway associated with VPC
* Two Public subnets 
* Two Private subnets
* Two Database subnets
* Database subnet group
* EIP
* NAT Gateway
* Public Route table 
* Private Route table
* Database Route table 
* Route table associations with subnets
* Peering with default VPC (if Required)
* Peering routes in acceptor and requestor route tables

# Inputs 

* Project name (mandatory) : User must supply their project name 
* Environment (mandatory) : User must supply their environment name
* vpc_cidr (Mandatory) : User must supply their VPC CIDR
* enable_dns_hostnames(optional) : defaults to true 
* common_tags (optional) : default is empty. User can supply tags in list(string) format.
* igw_tags(optional) : default is empty. User can supply tags in list(string) format.
* public_subnet_cidrs(Mandatory) : User must supply only 2 valid public subnet CIDR.
* public_subnet_tags (optional) : default is empty. User can supply tags in list(string) format.
* private_subnet_cidrs(Mandatory) : User must supply only 2 valid public subnet CIDR.
* private_subnet_tags (optional) : default is empty. User can supply tags in list(string) format.
* database_subnet_cidrs(Mandatory) : User must supply only 2 valid public subnet CIDR.
* database_subnet_tags (optional) : default is empty. User can supply tags in list(string) format.
* db_subnet_group_tags (optional) : default is empty. User can supply tags in list(string) format.
* nat_gateway_tags (optional) : default is empty. User can supply tags in list(string) format.
* public_route_table_tags (optional) : default is empty. User can supply tags in list(string) format.
* private_route_table_tags (optional) : default is empty. User can supply tags in list(string) format.
* database_route_table_tags (optional) : default is empty. User can supply tags in list(string) format.
* is_peering_required (optional) : Defaults to false
* vpc_peering_tags (optional) : default is empty. User can supply tags in list(string) format.

# Outputs
* vpc_id: VPC ID created
* public_subnet_ids: list of 2 public subnet ids created
* private_subnet_ids: list of 2 private subnet ids created
* database_subnet_ids: list of 2 database subnet ids created