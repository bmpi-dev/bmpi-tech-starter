## K8S Cluster Cost Compare

![](https://pbs.twimg.com/media/C-NknkeUwAAxSQs?format=jpg&name=large)

In theory the set of services required to run a web app on Kubernetes is relatively simple. You will need:

- A Kubernetes master (manager)
- Worker nodes (instances/VMs)
- A load balancer
- Some block storage
- VNet (Public IPs, DNS zone)
- Container Registry (Optional)

Note: **The following assumptions only consider the development and test environment, so there is only one woker node and only one available area**.

### AWS

- Kubernetes master $2.40 per day
- Nodes (1) x (2 vCPU 4GB RAM) $1 per day
- Load balancer ~$1.00 per day
- Disk (TBD)

total $4.4 per day ($132 per month)

### GCP

- Kubernetes master $2.40 per day<sup>1</sup>
- Nodes (1) x (1 vCPU 3.75GB RAM) $1.14 per day
- Load balancer ~$0.60 per day
- Disk (TBD)

total $4.14 per day ($124.2 per month)

Note<sub>1</sub>: if you are running a cluster in only a single zone, you will not incur this fee.

### Azure

- Kubernetes master (free)
- Nodes (1) x (2 vCPU 4GB RAM) $1 per day
- Load balancer ~$0.61 per day (Optional, can be replaced by basic type, but it needs k8s be created by CLI not web console)
- Disk (128G) $0.6 per day
- Container registry $0.6 per day
- VNet $0.2 per day

total $2.4 - $3.01 per day ($72 - $90.3 per month)

### DigitalOcean/Vultr

- Kubernetes master (free)
- Nodes (1) x (2 vCPU 4GB RAM) $0.67 per day
- Load balancer $0.33 per day (Optional)
- Disk (Can use OS disk, 80G * 2, free)

total $0.67 - $1 per day ($20 - $30 per month)

## K8S Resource(CPU/Memory) Cost

![](https://pbs.twimg.com/media/FDA39DEVIAEku8p?format=jpg&name=4096x4096)

![](https://pbs.twimg.com/media/FDA4QnVVIAA21AA?format=jpg&name=4096x4096)

Kube system use memory is 2G(12 Pods), almost half of the Node's memory(4G).

## Infra service

- [Convox](https://convox.com/)

## Reference Links

- [Run Kubernetes in Azure the Cheap Way | Thomas Stringer](https://trstringer.com/cheap-kubernetes-in-azure/)
- [Cheap AKS Update - Basic Load Balancer | Thomas Stringer](https://trstringer.com/cheap-aks-load-balancer/)
- [Cost of running k8s](https://convox.com/blog/cost-of-running-k8s/)
- [DigitalOcean Kubernetes Without a Load Balancer - Mike Cartmell's blog](https://mike.sg/2021/08/31/digitalocean-kubernetes-without-a-load-balancer/)
