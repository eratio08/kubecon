# Day 2

## Keynote: Kubernetes Project Updates

> SIG: Special Interest Group

Updates of 
* K8s
* Open Cluster Management
* K8s Steering Committee: Splitting Chair & Technical Leads.
* SIG Docs: 15 different languages, german and polish need support. (but only k8s member can contribute)
* K8s 1.27.0 got released
* SIG CLI project
* SIG security
* Containerd


## Sponsored Keynote: Open Source in Bloom 🌼 at AWS - Nathan Taber, Senior Product Manager, Amazon

Charters:
1. trusted reliable secure k8s
1. vibrant community

Sustainability is critical for aws.
Contributions: 
* 10M$ for openSSF
* patent
* resources for cnd
* registry.k8s.io migration

OSS is used as the basis of everything.

K8s at scale observations:
* choice matters, undifferentiated heavy lifting
* security requires constant effort
* more than stateless micro services, any kind of workload


## Keynote: CNCF Incubating Project Updates

* Backstage: huge adoption.
* Cert Manager: k8s cert management automation.
* Cilium: eBPF, service mesh, ingress, spiffe mtls.
* Cloud Custodian: rule engine for the cloud.
* Cloudevents 
* cri-0: runtime like containerd
* dapr: portable, event-driven runtime to build cloud native apps
* Dragonfly
* emissary ingress
* Falco
* gRPC: 14+ languages, up-coming service mesh, observabillity
* in-toto: security claim verification, attestation types
* istio: service mesh
* Knative
* Longhorn: distributed storing system
* NATS


## Sponsored Keynote: Total Clarity on Your Application Security - Guillaume Sauvage de Saint Marc, Vice President, Engineering, Emerging Technologies and Incubation, Cisco

Tools for secure applications.
98% of industry acknowledge security is key.
![](./Screenshot%202023-04-20%20at%2009.31.29.png)

story: a blurry image and clarity on certain aspects of the image.
Just seeing aspects does not help, you need a total clarity.

![](./Screenshot%202023-04-20%20at%2009.34.06.png)

Tools: Kube calrity, VM clarity, API clarity


## Keynote: Tales from the Cloud Native Community - Nikhita Raghunath, Staff Software Engineer, VMware & Ricardo Rocha, Computing Engineer, CERN

CNCF TOC; 11 members, seats from maintainers & end users.
They evacuate the projects in the cncf and their maturity.
Sandbox, Incubating, Graduated, Archived.
Challenge: huge growth.

Keycloak, argo, gluc, open kruise, kube vela are not in incubation.

Huge diversity of submission when looking at sub categories.
Provisioning is on the rise.
TAG: Technical Advisory groups.
Security is on the rise, a lot of submissions.

![](./Screenshot%202023-04-20%20at%2009.42.37.png)

What is the TOC working on.
* Cloud native guide points. Steps to improve majority of cncf projects. All about guidance.
* Also rework criteria for the stages. 
* Huge project list of CNCF is beautiful chaos. No gate keeping to drive innovations.
* Working an ways on how to explore the huge space of projects

TAG:
* Security: supply chain policy projects and white papers
* Runtime: edge/batch whie papers, CDI support in container runtimes, proposal for WASM
* App Delivery: plarforms white papers, tag-app-delivery.cncf.io
* Strogae: new white paper DoKC
* Environmental Sustainability: Carbon Intensity, Sustainability Chapter in the gitops group
* Observabillity: vision for Otel, observability query, language standards for queries
* Network: meshry playgorund play.meshery.io
* Contributor Strategy: Mentoring, Contributor, Growth


## Keynote: Gardens and Glaciers: Saving Knowledge Through Succession - Emily Fox, Security Engineer, Apple

> Leave it netter than you found it.

A lot of metaphors about how to convey knowledge and maintain it.
Sadly a lot of bla bla.

## Keynote: MLOps on Highly Sensitive Data - Strict Confinement, Confidential Computing, and Tokenization Protecting Privacy - Maciej Mazur, Principal AI/ML Engineer, Canonical & Andreea Munteanu, AI/ML Product Manager, Canonical

Genome-driven drug discovery.
Use ai to develop medicine tailored to a genome.

MLOps: settings up processes sampling to doctor room to public cloud.
You need to follow a lot of compliance to ensure data privacy.
They use Tokenization during sampling.
Find PII and turn in to e.g. UUIDs.
It needs to be tamper safe, use microK8s.

Is using the public cloud safe?
Use confidential computing.
Use images open enclave etc, Confidential Containers.
Azure support that.

![](./Screenshot%202023-04-20%20at%2010.17.54.png)

kubeflow pipeline, to build the entire solution.


## Keynote: Closing Remarks

--


## Rotate Roots Right Round: Using Cert-Manager for Safer Private PKI - Ashley Davis, Jetstack

> cert-manager is the easiest way to automatically manage certificates

Seems to be the only tool to do that in the landscape in the cncf.

Where to get the cert from?
Vault, let's encrypted, other.

What's PKI?
Public Key Infra.
Chains of certs.
Private PKIs, chains that you control.
It's cost-efficient.
Total control offers certs.
Has no artificial rate limits.
Let's encrypt is not suitable for private PKIs for that reason.

Certs are required for mtls.

Root Cert -> Intermediate Cert -> Leaf Certificates.
Self signed: cert signed with it's own private key.
Leaf cert is the identity cert.
You do not need this architecture.

Risks of PKI.
Not a free lunch.
1. Not locking things down. CA issuers should not issue anything. Use approval policies.
1. Root Rotation. Have a plan. Hard to automate.
1. Trust. If you cant trust the CA, the certs are useless.

Sage Private PKI.
There is repo, but don't copy it.

### 1. Issuer

Simple approach is in-cluster.
User cert-manager.

![](./Screenshot%202023-04-20%20at%2011.12.16.png)

Root can have a longer lifetime.
Have a rotation policy.

### 2. Cluster issuer

![](./Screenshot%202023-04-20%20at%2011.13.07.png)

Have policies to not issue unexpected CA certificates.
Not issue privileged domains.
Shorter lifetimes.

![](./Screenshot%202023-04-20%20at%2011.14.26.png)

In prod: restrict dns names and keep max duration as low as possible.

### 3. Trust

Use the trust-manager, another project.

![](./Screenshot%202023-04-20%20at%2011.15.52.png)

Pods mount the resulting config map and trust the CA.
Using the bundle means we only have to one thing to update.
So no backed in CAs.

Don't use `ca.crt` from the root.
If cert it changed in-place, trust is lost.

Hot to scale it?
How to rotate?
Rotating intermediate is easier?
Not in a disaster case.
So practice root rotation.
Revocation is not worth it.
So do root rotation.

How to make is safe with no downtime.
1. Create the new root cert
1. add root to the bundle
1. Ensure everything is using the new bundle (Hard part!, you might not know)
1. Shift issuance to the new root
1. Remove old root

![](./Screenshot%202023-04-20%20at%2011.22.51.png)

Key Point 1: Your architecture matters.
With a good cluster it might be simpler.
But multi cluster is hard because of the distributed trust.

Key Point 2: Rotation is Key.
You need a plan to rotate.
Rotation is not hard on it's own.
It takes time and you need to practice it.

Key Point 3: Revocation isn't' reliable
You need a rotation plan anyway.

Key Point 4: Try Private PKI
Safes money and time.

![](./Screenshot%202023-04-20%20at%2011.27.27.png)


## Kubernetes Defensive Monitoring with Prometheus - David de Torres Huerta & Mirco De Zorzi, Sysdig

Falco: Look inside of kernels and create rules and alerts.

> When the only tool you have is prometheus everything looks like a metric.

History data allows for anomaly detection.
Quick Intro to anomaly detection:

Group anomaly

![](./Screenshot%202023-04-20%20at%2012.04.15.png)

Over time
![](./Screenshot%202023-04-20%20at%2012.04.54.png)

Seasonality anomaly detection
![](./Screenshot%202023-04-20%20at%2012.05.21.png)
![](./Screenshot%202023-04-20%20at%2012.05.47.png)

Thread detection.
* Check if api server has 401/403
* Do these checks for secrets or config maps, cluster API
* Track general CRUD actions on the cluster API
* tack new ingress creation
* check near to expire certificates, to prevent mitm attack on expired certs
* track 404, 403 request / request rate. 404 might be a finger printing attempt, 403 might brute force, 500 could also be someone breaking something
* high inode usage across the cluster, can detect ddos.
* Abnormal CPU usage take all containers of the same name and compare of one of them uses more cpu than all others, could be crypto mining
* abnormal outbound traffic, might be exfiltration, e.g. DB dump
* check out bound package size, massive exfiltration

Take historical data.
Visualized infrastructure topology.
Over time you can detect deletion, added or changed resources.

Service Meshes also emit metrics.
You can visualize network topologies.
You can see who is talking to whom.

Monitoring with falco.
With a sidekick deployment you get rich labels.
Detect if rules activation changes, high number of critical events.
Numbers of errors in the output.


## Image Signing and Runtime Verification at Scale: Datadog's Journey - Ethan Lowman, Datadog

Datadog runs on many self-hosted k8s.
So the solution must work on that scale.

Why signing & verifying?
The pipeline with 3rd party tools increases the surface of attacks.

![](./Screenshot%202023-04-20%20at%2014.36.53.png)

Push signing to the left and verificaton to the right.

Modern consensus on image sinning.
The container registry has to store the signatures.
How to connect the signer to the verifier is not standardized.

![](./Screenshot%202023-04-20%20at%2014.37.35.png)

Registries are a known runtime dependency.
Signature replication is a solved problem for container registry.
The approach is based on sigstores's cosign approach.
Using an open standard is recommended.

Signature format

![](./Screenshot%202023-04-20%20at%2014.42.19.png)

Signature envelope

![](./Screenshot%202023-04-20%20at%2014.42.53.png)

To store the envelopes in a format that is supported by the registry use OCI Layers.

The signature location is a modification of the image storage location.
So there is a different quota on the signature than the image.

Signing Service
![](./Screenshot%202023-04-20%20at%2014.45.22.png)

Signing Thin client

`ddsign`, they have helpers for docker, a cli, and a bazel rule.

Why not signing directly with HashiCorp Vault?
Audit Logs are not detailed enough.
The signing service allows for detailed audit logging.
The signing service also encapsulate the complexity of singing behind a simple api and deployable artifact.
Also is allows for deduplication is possible.
Only create new signatures if signatures changed.
Key management is hidden from client.

Verification.
Trade-off: the earlier you verify, the earlier you get developer feedback. 
Closer to runtime gives more integrity.
Do multiple verification.
At DD verification is done on the node container runtime.
Validating with admission webhooks.

![](./Screenshot%202023-04-20%20at%2014.52.37.png)

Webhook runtimes add the API server response time because it block in webhooks.
So this will not work as it take up on avg. 200ms and the goal is p90 of 10ms.

Workaround use other webhook `ImagePolicyWebhool` it has caching but this is not stable enough.

Other approach: verification in containerd.
Integration point after image digest and before image pull.
They forked containerd, so there is an upstream pr to get this into containerd.
It runs plugin code to determine if an image should be pulled.
Make it resilient with verification retry.

Currently only possible because of the self-hosting.
Will be hard for managed clusters.
Hope for CP will support that soon.

Developer Perspective:
The kubelet events will show the issue if a verification failed.

How to distribute the verification config to the node?
Verifier plugin on each node.
Has public keys, verification mode, audit, block or disable.
Image digest revocation list.

Requirements:
No new node dependencies, slow staged rollout of config, multiple fallback mechanics.

Layered approach:
![](./Screenshot%202023-04-20%20at%2015.02.00.png)

Distributing the revocation list.
Bake it into the node image on build.
Update via node rollout
Dynamic updates would be useful because container runtimes cache images.
Rather drain node.

Challenges:
Verification mode by cluster namespace does not work easily.
Use dedicated cluster for sensitive workloads.

Monorepos make it easier when using Bazel.
Role out audit mode before.

Node level verification is uncharted territory.

Takeaway:
1. Evaluate image signing as a service for security and scalability.
1. Think about the reliability risk of k8s admission webhooks and advantages of node-level verification.


## Checking the Chains at the Gate: Building Supply Chain Policies with Gatekeeper and Ratify - Jeremy Rickard, Microsoft
State of building & shipping services today.
* a lot of tools helping
* thing get faster
* its easier than ever, but is more complex to run them
* things get even harder with regulations, e.g. SBOM

Now more tools... yay.

Can we use new things to make automated decisions?
How do we enforce thins in cluster?
If we use 1.26 or later we get policies.

Could use admission controllers.

![](./Screenshot%202023-04-20%20at%2015.32.22.png)

Validation can be done here.
Downside: write or run components in the cluster.

OPA Gatekeeper project.
How does it work in this scenario.
Base on the OPA.
Write policy in their lang

New concepts:
ContaintTemplate

![](./Screenshot%202023-04-20%20at%2015.34.16.png)

Here requires labels.
Now actually policy.

![](./Screenshot%202023-04-20%20at%2015.34.54.png)

If difference detected, generate status message or error.
Gatekeepr can evaluate that and prevent deployment.
When the template exist define the constraint

![](./Screenshot%202023-04-20%20at%2015.35.33.png)

**DEMO**

We saw that missing label will prevent application to cluster.

Gatekeeper allows auditing.
We can see which namespace violate the policy.

How to deal with things that are not in the cluster?
E.g. Verification of images.
Block deployments base on the content of the image.
Block base on scan reports.
Gatekeeper allows for external data.
Define Provider that knows how to get the data.
The provider is used during policy evaluation if defined in the policy.

![](./Screenshot%202023-04-20%20at%2015.44.54.png)

How to distribute this external data?
Block storage?
How to associate?
OCI 1.1 has new API for referrers and artifacts.
Build graph of relations.
So you can get this information from the registry.
Using the `subject` block.

![](./Screenshot%202023-04-20%20at%2015.48.08.png)

**DEMO**

Having signed image and related sbom as OCI artifacts.
Using `ratify` as a ready build provider.
It provides a framework and plugable verifiers.
We can build a custom verified plugin to extend capabilities of ratify.
Tell ratify how to call the binary.
Source can be an OCI artifact again.
Install the plugin via CRD.
Here plugin is written in go.
Pushing using `oras`.
Ratify and Gatekeeper run in the cluster.
With the CRD in place ratify will download the binary and use the plugin.

The plugin infra allows for complex validation logic.

---
We should check when it's available:
*The Compliance Business Case for Kubernetes in the EU: Get Ready for EUCS - Robert Ficcaglia, SunStone Secure, LLC & Anders Eknert, Styra, Inc.*


## Running Not Root Made Easy - Luboslav Pivarc, Red Hat

kubevirt, run vm aside containers.
VMs run inside pods.
Transitioned to non-root pods.
Motivation: principal of least privilege.
Well know counter measure to prevent CVEs.
Pod security standards * other auditing tools.
Root in the container is root on the host.
K8s does not support user namespaces yet.

The goal: run nginx with user id 1000.

Access Control:
`UID : GID : OTHERS` (world).
`rwx:rwx:rwx`

Images: permission bits are encoded in the image as the image represents the data available.
Another problem here is that most package manager require root.

How to tackle the Nginx requiring root. 
* Strace on nginx and see which system call are made and which path are access.

Other approach:
* use `EmptyDir` empty volume bound to the lifecycle of the pod
* use `dive` to inspect the layer of the image
* DOCKERFILE COPY -chown

Assume we fixed all the FS permission issues.
Now the pod fails to bind to a port.
Adding net capabilities will not work.
A process has a set of caps.
Permitted, effective, inheritable,...

A new user will have not caps by default.

On app layer
1. find out whits caps are required
1. looks at effective set
1. ask kernel for missing in effective set
1. Continue with app logic

Using file capabilities
* requires mod of the iamge
* we need to set the cap on the app binaries
* `setcap`

`KEP 2763` Ambient capabilities in K8s. 

Case: we need to pass a GPU to the container.
Devices will have the same owner & groups of the host.
This is an issue.
Cri-o has a way to handle this.

Persistence Volumes & Claims.
If 2 pods share it uid and gid needs to be the same.
You could set `fsGroup` to this.

For block volumes:
`fsGroup` will not work here.

**ACTUALY THIS APPROACH IS NOT EASY AT ALL**


## 🦝 Minimalism: Key to Cloud Security - Barun Acharya, Accuknox

*talk didn't happen*


## Disaster Recovery: Bringing Back Production from Scratch in Under 1 Hour Using KOps, ArgoCD and Velero - Andre Jay Marcelo-Tanner, Ada Support

CKA & CKS Certs recommended.

An incident: 
* end of the day
* there is a problem for a few days
* deployments failing
* isolated to a single cluster
* new nodes to not connect to the cluster, whats going on?

The cluster managements tool used here is `kOps`.
It can generate terraform.
Supports zero-conf managed k8s add-ons.
YAML manifest based api configuration.
Templating and dry-run modes for creating manifests.
Multi-arch ready with arm64 support.
`kops create cluster` or `kops update cluster`.

Kops showed a lot of diffs, they applied anyway.
In this case the worst thing happens and prod went down.
A lot of service do not work e.g. coredns.

Disaster Recovery Plan.
Run them once or twice a year.
They use `velero` to backup the cluster.
Have it running on a schedule.
Persistent Volumes Backups.
Backup can be stored in a block storage.
`velero backup create`, `velero restore create`,
This did only partially work in this case.

Let's recreate the whole cluster.
So deleting the whole cluster, on purpose.

ArgoCD:
* installed it
* gitops tool, deploy app via single source of truth
`argocd create app x`

Not every thing worked well,
* manual installs
* outdated guides

41 min delete and restore the cluster, only 2h outage.

Actually cause of an issue was the kOps state store.
The s3 bucket had a lifecycle policy.
State was deleted after 90 days.

Lessons learned
* complete migrations, use unified way of deployment
* be expert of your tools
* always practice the disaster recovery

ArgoCD Everywhere!
GitOps FTW.

Using GitOps repo.
Everything exists in argocd.
No manual deployments.

![](./Screenshot%202023-04-20%20at%2017.51.35.png)

![](./Screenshot%202023-04-20%20at%2017.52.41.png)

They use blue/green cluster updates of k8s.

*I really want to try out ArgoCD!*

![](./Screenshot%202023-04-20%20at%2017.55.25.png)
