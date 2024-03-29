# Hub & Spoke : 

https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/decision-guides/software-defined-network/hub-spoke

In the hub and spoke model, the hub is a virtual network that acts as a central location for managing external connectivity and hosting services used by multiple workloads. The spokes are virtual networks that host workloads and connect to the central hub through virtual network peering.

![image](https://user-images.githubusercontent.com/40743779/209608094-ed06b329-6b7b-4121-a52c-087de9254543.png)

# Point to Point model

https://transportgeography.org/contents/chapter2/geography-of-transportation-networks/point-to-point-versus-hub-and-spoke-network/

A point-to-point network connects directly to a set of locations without any interruption of services (e.g. pick up or drop off) even if the route itself may not be direct. A (pure) hub-and-spoke network connects every location through a single intermediary location called a hub. 

![image](https://user-images.githubusercontent.com/40743779/209608124-7fd28917-aec9-400e-a895-983d90875be8.png)

