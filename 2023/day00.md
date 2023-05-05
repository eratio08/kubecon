# Day 00 AWS Container Day ft. Kubernetes

## Keynote

Why Kubernetes
- Ease
- Consistency
- Ecosystem
- Communication

Principals
- Security Fist
- Build for production
They wanted to make it open source, shifted development to the open.
Here is was not about doing the thing like with redis, but adopt K8s and not make it an AWS product of it's own.
Native and upstream.

Did a lot of contribution to things like OTEL, Fluentbit, tinkerbell containerd, K8s, cortex.

Here the stream had some technical issues...

### K8s Portfilio
<screenshot>

### Security | Build for production
Patches embargoed CVEs

Seamless cloud integrations, high level EMR & Guardduty, Supporting (sqs, dynamo),...

### Recent upstream work:
gzip default for kube-apiserver -> 80% improvements for 'list' calls,

etcd, static ips and static volumes, improves MTTR and cluster updates

registry.k8s.io change: split registry source to be vendor neutral, allows to set registry to the local data center
(google worked with aws here)

### Karpenter

right node in the right place,
improve efficiency and right size nodes,
also down scaling,
it's ready for production

### EKS Console

See everything, with deep link to aws resources.
It works with any k8s cluster, not only eks.

It integrates metrics.

### EKS Addons

lifecycle management by clients.

### CloudFormation Template Sync for Flux

Flux for gitops, it's open source

### Coming Soon
 
IAM cluter access management, will be simplified.
Will merge the 2 models (ima, k8s).

### VPC Lattice

Improving the networking.
Connect service across VPC/Accounts.
Granular access controls.
Application traffic controls.
With build in observeability.

### Gateway API Controller

K9s api for VPC lattice.

### Guard Duty

It's ML backed and thread intelligence.

### EKS Runtime Monitoring

File access, process execution, network.
Pod-level activities.

Defense in Depth-style.
Will work even if guard duty agent is disabled.
Looks at audit logs, system events.


## AWS JAM

It's a digital escape-room event.


## Building your data pipeline in Amazon EKS using Argo Workflows and Events 

did miss this one,

They talked about EKS blueprints and gitops with argo.


## Build secure and scalable connectivity for modern applications on AWS

* https://awslabs.github.io/data-on-eks/docs/job-schedulers/argo-workflows-eks
* https://awslabs.github.io/data-on-eks/
* https://aws.amazon.com/blogs/containers/dynamic-spark-scaling-on-amazon-eks-with-argo-workflows-and-events/


## Whose Kubernetes is it anyway? 
missed


## How to optimize costs at scale with proper governance controls and observability
missed


## Afternoon Keynote
missed


## Kubernetes threat detection, investigation, and incident response automation
mostly missed

Cluster Audit logs can be checked,
Guard Duty has EKS Protection that checks runtime events.


## Operating Open Telemetry Collector for Scale and Resiliency in Container environments

ADOT = AWS Distro for OpenTelemetry.

Otel tries to solve the issue of too many agents in the cluster.

The disto is a production ready distributon of the otel collector.

Deployment options: no collector, agentmode, gateway mode.
No collector, the app will send on it's own, using the otel sdk, more load on the app.
The agent-mode is the decentralized approach. 


## eBPF based node telemetry and visibility on EKS

Considerations for containerized workloads: network isolation, observability, security.

With CNI plugin pod get ips from the vpc cidr space.

eBPF run sandboxed programs in the operation system kernel.

Kprobes to detect resource exhaustion.


## Future proof your Kubernetes cluster for cost optimization

CNCF: Every org usind k8s will increase cost by 68%.

Control plane is a fixed cost.

Workloads, network cost and observability cost.

Most containers use <30% of cpu (datadog surway). 
Use compute saving plans & reserved instances.
Use Kubecost to optimize pods.

To optimize nodes, use arm and spot instance.
Arm is up to 40% cheaper.

Autoscaling: cluster auto scaler, so scale up and down the node groups.

Karpenter can be used for optimization.

Namespace resource quotas, to e.g. reduce loadbalancers used.

Network cost: cross az cost.
How to minimize that?
Use the 'zone' label.
Topology aware hints.
Kube cost helps to detect these.
IP mode is cheaper than instance mode for AWS LB controller.

Observeability: use managed grafana/prometheis.
Use ADOT.
Optimize logs: different kinds of logs.
Filter with otel.


## Running Kubernetes workloads at scale

missed

