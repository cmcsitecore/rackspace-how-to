---
permalink: floating-ip-faq/
audit_date: 
title: Floating IP address FAQ
type: article
created_date: '2016-05-18'
created_by: Jorge Miramontes
last_modified_date: '2016-06-01'
last_modified_by: Kyle Laffoon
product: Cloud Networks
product_url: cloud-networks
---
Get quick answers to questions about the Early Access (EA) release of the floating IP addresses feature for Rackspace Cloud services.

###Early Access

#### What are floating IP addresses?

A floating IP address is a static IP address that has the ability to move or “float” between cloud resources within a region, primarily cloud servers. It is reserved at the tenant level and does not need to be associated with a specific port on a VM.

#### Where is the documentation?

API guide: 
Documentation for the EA release will be available soon, and this FAQ will be updated with links to it.

Getting Started:
Documentation for the EA release will be available soon, and this FAQ will be updated with links to it.

#### What makes a floating IP address better than a fixed IP address?

Floating IP addresses enable you to reserve an IP address if you terminate your cloud server. This ish important for a few reasons:
 - Constantly changing cloud resources – Creating and removing cloud resources is a common exercise. However, each time you create a new cloud resource, the default fixed IP address provided changes, which requires updates to configuration files, DNS entries, and so on. Using floating IP addresses enables you to keep the same IP addresses no matter how many times resources are created and removed.
 - IP address reputation – An IP address can have a reputation. Some IP addresses have good reputations and become whitelisted by trusting sources across the Internet. More importantly, however, some IP addresses have bad reputations and get blacklisted. If you happen to get a “bad IP address,” your infrastructure can become unreachable by certain areas of the Internet. Using a floating IP address enables you to build a good reputation for an IP address and keep it.


#### Is this feature supported for all Rackspace Cloud customers?

This feature is supported for cloud-only customers, but only if they are provided access via the EA signup page located [here](https://one.rackspace.com/display/compute/Floating+IP+EA+Signup). For more information, see [What are the features only for EA?](####What are the features only for EA?)

#### What features are supported for EA?

The EA release supports the ability to create, associate, disassociate and delete floating IP addresses.

#### Are floating IP adderesses supported via the neutron client?

Yes.

#### Is this feature available from the Cloud Control Panel?

For EA release, no. We plan to provide Cloud Control Panel support for Limited Availability and later.

#### Are floating IP addresses supported for OnMetal users?

No, floating IP addresses are currently supported only for virtual cloud servers.

#### Are floating IP addresses supported for RackConnect v3.0 users?

No, floating IP addresses do not work with a RackConnect v3.0 cloud network.

#### Is there a limit on the number of floating IP addresses that a tenant can have?

The default limit is 5 floating IP addresses per tenant. You can create a support ticket to raise the limit, but requests might be temporarily denied depending on capacity.

#### How is floating IP address different from a shared IP address?

A shared IP address is used for active/passive high availability (HA), where one IP address is needed between two or more servers for the purpose of redundancy (active-standby). The IP address is owned by one of the servers at any given time, and clients or other servers use this IP address for communication with the HA pair. 

Although a floating IP address can be used to solve the active/passive HA problem, it would require monitoring and API calls to achieve the same result. Thus, a shared IP address is the preferred method to solve the active/passive HA problem.

#### Can existing cloud servers' public IP addresses be used as floating IP addresses?

No, the floating IP addresses are a new pool of IP addresses. You can't migrate existing IP addresses on your cloud servers to become floating IP adresses.

#### Can we migrate FirstGen customer IPs to be Floating IPs?

No.

#### Can I migrate First Gen customer IPs to be Floating IPs?

No. Do not add or disconnect networks . Doing so causes serious issues with
networking on the Vyatta appliance and the only recourse will be to rebuild the
Vyatta appliance.

#### What do I need to know when I associate a floating IP address with my cloud server ?

Because cloud servers come with a fixed public IPv4 address you can remove the fixed IP address and replace it with a floating IP address. If a you want to keep your fixed IP address in addition to a floating IP address. If you want to keep the fixed IP address in addition to using the floating IP address, then you need to configure the  server to handle traffic appropriately. For details about how to do this, see the API and How-To documentation.


#### What are the features limitations for EA?

 - Floating IP addresses are intended to work only with Next Gen Cloud Servers. Floating IP addresses do not work with other products such as OnMetal, Cloud Load Balancers, and RackConnect v3.0.
 - Yo can't convert current public IPv4 addresses cannot be converted to a floating IP addresses. You must provision a new floating IP address.
 - The quota is limited to 5 floating IP addresses per tenant. Quotas will be raised during Limited Availability and later.
 - There is no support for floating IP addresses in the Cloud Control Panel.
 - Currently, the feature supports only IPv4.