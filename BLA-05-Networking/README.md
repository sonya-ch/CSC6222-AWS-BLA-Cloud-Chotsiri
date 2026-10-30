# AWS Networking & Content Delivery
## BLA5 AWS Cloud — Study Guide
## Topics: Amazon VPC, Subnets, Route Tables, Internet Gateway, NAT Gateway, Amazon Route 53, and Amazon CloudFront.

### 1. Overview
AWS networking services help you isolate cloud resources, control network traffic, resolve domain names, and deliver content efficiently to users.

#### Service / Concept	Main purpose
* Amazon VPC	Creates a logically isolated virtual network in AWS
* Subnet	Divides a VPC IP address range into smaller networks
* Route table	Determines where network traffic is directed
* Internet Gateway (IGW)	Enables internet connectivity for appropriately configured VPC resources
* NAT Gateway	Allows private-subnet resources to initiate outbound IPv4 connections to the internet
* Amazon Route 53	DNS service for domain-name resolution and DNS routing
* Amazon CloudFront	Content delivery network (CDN) that can cache and deliver content from edge locations

### 2. Amazon VPC
 Amazon Virtual Private Cloud (Amazon VPC) is a logically isolated virtual network in an AWS Region.

#### With a VPC, you can configure:
* IPv4 and, where needed, IPv6 address ranges.
* Subnets across Availability Zones.
* Route tables and network connectivity.
* Network security using security groups and network ACLs.
* Connectivity to other networks and AWS services.
* CIDR notation
* CIDR defines an IP address range. For example, `10.0.0.0/16` is a common private IPv4 range for a VPC.
* A smaller prefix number represents a larger address range. For example, `/16` contains more IPv4 addresses than `/24`.
* Plan CIDR blocks to avoid overlapping ranges when networks may need to communicate.

### 3. Subnets
A subnet is a range of IP addresses within a VPC. Each subnet belongs to one Availability Zone.

#### Public subnet
A subnet is commonly considered public when its associated route table has a route to an Internet Gateway. Resources also need suitable IP addressing and security configuration to communicate with the public internet.
#### Typical uses:
* Internet-facing load balancers.
* Public-facing resources that require direct internet connectivity.

#### Private subnet
A private subnet does not have a direct route to an Internet Gateway for ordinary internet access.
#### Typical uses:
* Application servers.
* Databases.
* Internal services that should not be directly reachable from the public internet.
* Important: A subnet's name does not determine whether it is public or private. Routing and resource configuration do.


### 4. Route Tables
A route table contains routes that determine where traffic is directed. Each route has a destination and a target.

#### Example routes for a VPC with CIDR `10.0.0.0/16`:
* Destination	Target	Meaning
* `10.0.0.0/16`	`local`	Allows routing within the VPC's address range
* `0.0.0.0/0`	Internet Gateway	Sends otherwise-unmatched IPv4 traffic toward the internet gateway
* The VPC local route is normally created automatically. A subnet uses its explicitly associated route table, or the VPC's main route table if it has no explicit association.
* AWS selects the most specific matching route for a destination.

#### Internet Gateway (IGW)
* An Internet Gateway attaches to a VPC and enables internet connectivity when routes, IP addressing, and security settings are configured appropriately.
* For typical inbound/outbound IPv4 internet connectivity, a resource generally needs a public IPv4 address, a route through the IGW, and security rules that allow the traffic.

#### NAT Gateway
A NAT Gateway can allow resources in a private subnet to initiate outbound IPv4 connections to external destinations without making those resources directly reachable through unsolicited inbound internet connections.
#### Typical setup:
* Create a NAT Gateway in a public subnet.
* Ensure that subnet has a route to an Internet Gateway.
* Configure the private subnet's route table to send internet-bound IPv4 traffic (commonly `0.0.0.0/0`) to the NAT Gateway.
* NAT Gateways incur charges. Review pricing and remove test resources when they are no longer needed.


### 5. Amazon Route 53
* Amazon Route 53 is AWS's scalable Domain Name System (DNS) service.
* DNS helps translate human-readable names, such as `example.com`, into information used to locate services.

#### Hosted zones and records
* Public hosted zone: Stores DNS records intended to be resolvable through public DNS.
* Private hosted zone: Stores DNS records for use within associated VPCs.
* A record: Maps a name to an IPv4 address.
* AAAA record: Maps a name to an IPv6 address.
* CNAME record: Maps a name to another domain name, subject to DNS rules.
* Alias record: An AWS Route 53 feature that can point a name to supported AWS resources, such as certain load balancers or CloudFront distributions.
* For a domain registered elsewhere, you may need to update the registrar's name-server settings to delegate the domain to the public hosted zone's name servers.

#### Route 53 routing policies
* Simple routing: Routes using a basic record configuration.
* Weighted routing: Distributes DNS responses according to configured weights.
* Latency-based routing: Directs users toward an endpoint selected based on network latency measurements.
* Failover routing: Supports active-passive configurations with health-check-based failover.
* Geolocation routing: Routes based on the geographic location of the DNS query source.
* Geoproximity routing: Routes based on the geographic location of users and resources, with optional bias.
* IP-based routing: Uses the IP ranges of DNS query sources.
* Multivalue answer routing: Can return multiple healthy records in response to a DNS query.
* DNS routing policies affect DNS answers; they are not the same as VPC route tables.


### 6. Amazon CloudFront
Amazon CloudFront is a content delivery network (CDN). It uses a global network of edge locations to deliver content closer to viewers.

#### How it works
* A viewer requests content through a CloudFront distribution domain name or configured custom domain.
* CloudFront processes the request at an edge location.
* If a valid cached response is available, CloudFront may serve it from the cache.
* If the content is not cached or requires revalidation, CloudFront may retrieve it from the configured origin.
* CloudFront returns the response to the viewer and may cache it according to the configured behavior.

#### Origins
An origin is the source from which CloudFront retrieves content. Examples include:

#### Amazon S3.
* An HTTP server or application endpoint.
* An Application Load Balancer.
* Benefits and considerations
* Can reduce latency by serving cached content closer to viewers.
* Can reduce repeated requests to the origin.
* Supports static and dynamic content, depending on configuration.
* Supports HTTPS and integrates with AWS security services.
* Cache behavior depends on TTLs, cache policies, request headers, cookies, query strings, and origin responses.
* For private S3 origins, Origin Access Control (OAC) can help restrict access so viewers use CloudFront rather than directly accessing the bucket, when configured correctly.



### 7. How the services work together
* Example: a globally accessed web application.
* Route 53 answers DNS queries for the website's domain.
* CloudFront delivers cached content and forwards requests to the configured origin when needed.
* The origin may be an Application Load Balancer or another application endpoint.
* The application's resources run within an Amazon VPC.
* Public and private subnets separate resources according to connectivity requirements.
* Route tables determine network traffic paths.
* An Internet Gateway and, where required, a NAT Gateway provide different forms of network connectivity.
* Not every architecture needs every service. Choose components based on the application's requirements.


### 8. Practical configuration checklist
#### 1. VPC and subnets
* [ ] Choose a non-overlapping CIDR range.
* [ ] Create the VPC and required subnets.
* [ ] Consider multiple Availability Zones for resilience.
* [ ] Verify each subnet's route-table association.
#### 2. Routing and connectivity
* [ ] Attach an Internet Gateway if public internet connectivity is required.
* [ ] Add the appropriate default route to the public route table.
* [ ] Confirm public IP addressing and security rules where needed.
* [ ] For private outbound IPv4 internet access, configure a NAT Gateway and the private route table if appropriate.
* [ ] Review security groups and network ACLs separately from routes.
#### 3. Route 53
* [ ] Create the correct public or private hosted zone.
* [ ] Add the required DNS records.
* [ ] If using an external registrar, configure the correct name servers.
* [ ] Verify record targets and allow for DNS caching/TTL behavior.
#### 4. CloudFront
* [ ] Choose and configure the origin.
* [ ] Review origin access and permissions.
* [ ] Configure cache behavior and viewer protocol policy.
* [ ] Configure a certificate and alternate domain name if using a custom HTTPS domain.
* [ ] Wait for deployment and test the distribution domain name.

---
## YouTube
* https://youtu.be/CxFtOFP1Qy4
* https://youtu.be/MN2Z9LSpgOg
* https://youtu.be/3n2Tb0hQuzg

## LinkedIn
* https://www.linkedin.com/feed/update/urn:li:share:7521757695192825857/
* https://www.linkedin.com/feed/update/urn:li:activity:7521758284140310528/
* https://www.linkedin.com/feed/update/urn:li:activity:7521758812668665856/

---

### 9. Troubleshooting hints
* A public subnet cannot reach the internet: Check the IGW attachment, route table association, `0.0.0.0/0` route, public IP address, security group, and network ACL.
* A private instance cannot reach the internet: Check the NAT Gateway, its public-subnet route, the private subnet's route to NAT, and security controls.
* A domain does not resolve: Check the hosted zone, record type and target, registrar name-server delegation, and DNS caching.
* CloudFront serves old content: Review cache policy and TTL; invalidate cached objects when appropriate.
* CloudFront cannot retrieve origin content: Check origin configuration, permissions, origin health, and network access.

Amazon Route 53 documentation
Amazon CloudFront Developer Guide
