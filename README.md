# Pro-Active Wireless Network Resource Management and Control

## Project Overview

OpenAPI is a blueprint implementation of a bidirectional application-to-network-interface with the goal to explore open interfaces in radio- and core-networks. This project is used as a demonstrator to kickoff discussions and to influence ongoing 4G and 5G standardization through rapid proof-of-concepts and early practical results. Our goal with OpenAPI is to understand the power of open interfaces in access and core networks. The approach is to specify and develop a set of open interfaces and to identify the most relevant parameters to improve user experience given various use cases while respecting net neutrality.
The OpenApi was tested against a 4-cell/2-eNB 4G white box system and a network comprised of [Open Compute Project (OCP)](https://www.opencompute.org) conform wifi white box access points.

## From Client-based to Network-based Mobility

The key questions addressed with this OpenAPI concept were:

* What are the benefits from active mobility management for the customer, network operator and service provider?
* What functions and interfaces in the network need to be added or opened to enable pro-active mobility management?
* What data needs to be collected to do most most efficient/effective decision making?
* How is the interoperability between existing and new mobility management system handled?
* Which new business models are enabled through an OpenAPI?

![client-based mobility](img/client.png?raw=true "client-based mobility")

What is the functionality required in the network to pro-actively influence certain mobility management decisions in order to optimize connectivity while respecting net-neutrality. Solutions are targeted that enhance the overall spectrum usage, reduce operational cost and overall customer satisfaction without discriminating user groups.

3GPP and none-3GPP mobility management for eNBs in 4G, gNB in 5G or Wifi Access Points mainly use signal strength as an criteria used by the user equipment to attach to the cell/wifi access point providing the highest signal strength. Systems relying on signaling strength have proven to work but imply that devices connect to a certain network with the highest signal strength, which (in a homogeneous wireless ecosystem) are most probably the physically closest ones.

This strategy is referred to as *client-based mobility* in the literature and scales well, but does not optimally utilizes the network nor optimizes user experiences. Whereas general connectivity is supported well with this client-based mobility approach, several scenarios cannot be supported. The knowledge collected and measured in the access- and core-network is not used for connectivity optimization.

![network-based mobility](img/network.png?raw=true "network-based mobility")

Example use cases are:

* Enable applications to signal application-level-requirements into the network such as required min/max bandwidth, level of importance, latency demands, or envisioned level of network reliability given.
* Enable the network to inform applications about the current network conditions and QoS-predictions of network parameters in terms of health status, application of network changes beyond 3GPP Rx-notifications in form of bandwidth, latency, health, jitter, etc.
* Support network telemetry to allow network-based mobility management and connectivity control for heterogeneous access/core network re-selection.
* Allow applications (none-time critical IoT sensors, firmware updates over the air of vehicles, etc.) to negotiate transmission windows (during night times and off-peak hours) for energy-aware and/or cheaper data transmissions.
* Compare rule-based and machine-learning-based approaches for mobility management
* Pro-actively evacuate users from bandwidth constrained networks (small cells or edge clouds) onto none-bandwidth-constrain networks (e.g. macro cells).

## High Level Architecture Overview

The figure below depicts the individual architectural components of the OpenAPI  with the green highlighted added functional blocks: GUI, OpenAPI and adapter-layer.

![client-based mobility](img/architecture.png?raw=true "architecture")

A machine-learning algorithm was implemented as part of this PoC but is not open-sourced. Instead a static rule is added to the project to illustrate the various API calls within a demonstrator.

![client-based mobility](img/ml.png?raw=true "machine learning")

## Software Repositories

Here is the lis of individual software repos used in this project.

[OpenAPI main Repo](https://github.com/att-innovate/openapi)

[eNB Log File Reader](https://github.com/att-innovate/openapi-enblogfilereader)

[OpenAPI GUI and Databases](https://github.com/att-innovate/openapi-gui)
