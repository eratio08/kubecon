# Day 1

## Keynote: Welcome + Opening Remarks - Priyanka Sharma, Executive Director, Cloud Native Computing Foundation & Chris Aniszczyk, CTO, Cloud Native Computing Foundation

159 CNCF Projects in 2023.
K8s can be start up in seconds using Kind.
Backstage was mentioned for DX.

Over 10k people attending the Con today.
58% are new attendee.
Next year will be in Paris and more people can attend.
March 19 - 22.2024.
KubeCon it back to china.
cdCon & GitOpsCon in Vancouver May 8-9.2023.

Cloud Native eco system: community is blooming.
159 projects as of today, that touch every aspect of cloud native.
1300 maintainers and 200k contributors.
52000 community group member (regional chapters).
406 Chapter, 24 K8s Community Days.

cncf.io/reports the journey report refresh.
K8s got a lot contributions from other enterprises.
Contribution did not slow down.
Open sourcing the new k8s security audit.

Occlusive Training & Certifications.
*We might want to check these out.*

EY and Hitachi joined the CNCF.
HCLTech InfoSys are new Platin Members.

Info sys joind the stage.
Infosys is top 3 global provider.
They to a lot of cloud native consulting and products.
Trends: Security, PaaS, Cost Optimization, Automation.

Platform Ops approach is also a goal of them.
They have the InfoSys Enterprise Application Developer Platform.

Alan Flower joins the stage.
HCL guy.
They have 1000 enterprise clients with k8s-based solutions.
220k employees.
They have a long history of supporting open source.
Joined Linux Foundation, Cloud Foundry Foundation, Sponsors CNCD, FinOps Foundation.
Now CNCF Platinum.

*We should checkout the FinOps Foundation.*

CNCF is an Open & Global Community.
155 Ambassador.

* mentoring.cncf.io
* glossary.cncf.io

*Inside Envoy* Film Screening today.

The speaker encourages contributions.


## Keynote: Tulips, Terabytes, and Transformations: Blooming Innovations in the Cloud Native Garden - Taylor Dolezal, Head of Ecosystem, Cloud Native Computing Foundation 

End User Community.
What available: **Wisdom of the Cloud** (newsletter).
60 min read.

You can get KubeCon all-access ticket a an enduser community member.

CTO Summit.
This con it's about **FinOps**.

![](./Screenshot%202023-04-19%20at%2009.44.55.png)


## Keynote: Cappucci-Know: Percolating EU End User Insights in the Cloud Native Café - Moderated by Taylor Dolezal

*Some Endusers enter the stage.*

Lunar, Mercedes Benz, Alliance, Hitachi.

How to state up to-date?
Mercedes Benz has a FOSS first Policy.
Contributing back is very important for them.
Staying up to date by contribution.

How has cloud native helped Lunar?
Unlocked velocity by adopting cloud native.
More autonomy increased velocity.
They have a developer platform that has sane default, and is compliant and secure.

Cloud native at alliance?
They decided to become digital sovereign.
Decision: Do I consume or do I create?


## Sponsored Keynote: Accelerate Sustainable Computing with Community Collaboration - Cara Delia, Principal Community Architect Financial Services and Sustainability, Red Hat & Huamin Chen, Senior Principal Software Engineer, Red Hat

1% of global energy consumption can be contributed to data centers.
Sustainable principles: better quality, access to latest innovation, ...

Fokus: efficient workloads, scaling, efficiency.

Project Kepler - capture engergy usage of workloads in the cloud.
Uses eBPF and ML to calculate power consumption.
With these metrics you can better scale workloads by tracking actual energy consumption.


## Keynote: CNCF Graduated Project Updates

Update from Envouy: ... Quite some updates.

Updates from Flux: flux is now a graduated project in the CNCF.
GitOps terraform.

Updates from fluentd: flientbit a lightweight agent.
Support for podman metrics.

Updates from Habor: 2.7 and 2.8 release.

Updates from LinkerD: 2.13 is released. 
Dynamic route requests. 

Updates from OPA: some.

Updates from Prometheus: 2.43 is out.
Out of order ingestion.
Improved memory usage.
New Alertmanager UI will be stream lined.

Updates from TUF: not sure what this does.

Updates Vitess: Scallable mySQL.


## Sponsored Keynote: Building a Sustainable, Carbon-Aware Cloud: Scale Workloads and Reduce Emissions - Jorge Palma, Principal PM Lead, Microsoft Azure 

How to build more sustainable software, using less energy.
A lot of country have defined goals in the context.

Green Software Principals: Energy efficiency, Hardware efficiency, Carbon Awareness.

Carbon-Awareness: Clean Energy - renewable.
Dirty Energy from fossile.

KEDA: A Event Driven Autoscalar for K8s.
Demand shaping: based on the carbon intensity.
Today uses a k8s operator.
Reads config map with cloud provider data to do scaling.
Carbon-Aware Scaler.

aka.ms/aks/kubeconEU2023


## Keynote: Building a Sustainable CNCF Project Contributor Base - Dawn Foster, Director Open Source Community Strategy, VMware

The problem is hard.
Humans are squishy.
We are unpredictable.
Open source needs humans to participate to sustain it.

Vicious cycle:
1. Not time to onboard
1. fewer contributors 
1. more maintainer burnout
1. back to 1.

We have complex motivations.
People want to be appreciated.
Actions: Be proactive and ask people for help on individual tasks.

Governance is all about humans.
Sets expectations on how people collaborate and make decision.
Action: Use templates to clearly document you governance.
(templates of the CNCF)

contribute.cncf.io/maintainers/templates

Onboarding Docs.
Good docs for onboarding is #1 step towards scaling maintainers.
Action: Use tempaltes and ensure to include dev env setup, running tasks and other requirements.

Diversity & Inclusion is important.
Action: Be proactive about including people and moving them into leadership roles.

Define a ladder of leadership roles, helps recruit new humans to reduce maintainer workloads.
Actions: Use templates and proactively require new humans and move up the ladder into leadership roles.

Mentoring.
Actions: Carve out some time for mentoring, shadowing or 1:1 time with other human.

Emeritus as a Goal.
Action: Be proactive about promoting new humans so that maintainers can move into emeritus roles.
Requires to move new people into maintainer roles.

Be strategic.
Do not try everything at once.
Onboarding docs is a good start.
Find people for different types of contribution.
Marketing or documentation, community management.

lists.cncf.io/g/cncf-tag-contributor-stately

Maintaining an OSS project is a lot of work.
Solution: find more humans to help.


## Keynote: Closing Remarks

--


## Zero Privilege Architectures - Thijs Ebbers & Diana Iordan, ING

Quite some places in the Netherlands are blow see level.
Looking away is not a good security proactive.
What's a good proactive?
Well designed assures.
There where some hard leanings with high water.

Adapt & Adjust: Megginson - Lessons from Europe for American Business.
It's not the stronger of the species nor the intelligence that survive, but the most adaptable to change.

How bad should it get?
e.g. Solarwinds etc.

What has gone wrong this least privilege?
e.g self updating agents.

Zero-Trust solutions?
Solarwinds showed it's not secure.

Nobody is in control of software lineage.
Zero-Trust implementation are over privileged.

The opportunity of defeating the enemy is prided by the enemy himself.
Know your weaknesses.

Typical dau: parching, scanning, generating, reporting.
But do more service help do tackle the issue?

*Bolting on security* to *Secure by design*.

You are playing for a Draw.
You should play for a Win.

![](./Screenshot%202023-04-19%20at%2011.12.22.png)

We should be very opinionated.

Carl von Clauswitz: A fast-moving environment can evolve more quickly than a complex can be adapted to it. By the time you have adapted, the target has changed.

Restore "Leas Privilege".
Perfection is archived if the is nothing left to remove.

Zero privilege.

No natural person in a production environment.

Principals:
* Every change is result of controlled proves, no single person can do changes
* any component is immutable yet ephemeral 

![](./Screenshot%202023-04-19%20at%2011.18.03.png)
![](./Screenshot%202023-04-19%20at%2011.21.32.png)

Automate everything.

Identifying the decision points.
Lesson: Stop compensating, solve the underlying issue.

![](./Screenshot%202023-04-19%20at%2011.20.14.png)

How to avoid fighting.
If there are not privileged accounts in the production env there is no risk of them getting over taken.

github.com/ing-bank 

Take waywas
* You are playing for a DRAW
* we need a parading shift
* play to win with a Zero-Privileges Architecture

![](Screenshot%202023-04-19%20at%2011.28.02.png)

`Book: Cloud Native Transformation`

CISA.gov secure-by-design guide lines.


## Confidential Containers Made Easy - Fabiano Fidencio, Intel & Jens Freimann, Red Hat

Confidential Container is a Project.
Kata Containers?

What are confidentials containers.
It's an imbrella project.
There is an Operator.
Other projects are: key broker, attestation agent attestation service ...and more.

A lot of companies are contributing.

Value Preposition: protect data-in-use at the pod level.
TEE (Trusted Execution Environments).
Make the use of TEE lift and shift easy.

Kata Containers: guest kernel, guest micro virtual machine.
Protects the host.

![](./Screenshot%202023-04-19%20at%2012.03.55.png)

How to get from Kata Containers to Confidential Containers.
We want to have encrypted memory.
Key broker and attestation service.
Protect host form non trusted workload
Protect workloads from each others.
Run on not trusted hardware.

Different flavors.
Provcess-based isolation. (SGX)
Vm-Based isolation. (SE, SEV-ES, TDX)

Cloud API Adaptor aka Peer Pods.
Remote hypervisor support.
CSP Vms as a guest vm (PodSandbox).

Use Cases:
* Regulated Industries: like health care.
* Government
* Banks
* ...

Case example: health care.
App running in a cloud protected by TEE.
Using attestation service to ensure what runs is expected.
(There are many model for attestation)

Other use case:
![](./Screenshot%202023-04-19%20at%2012.12.17.png)

Key will be provided after attestation.

**DEMO** (asciinema)

Deploy the operator into the cluster (using kubectl).
Now install and add a CRD.
Apply and the controller will monitor the CRD and install a Daemonset.
It creates the runtime classes.
Binaries are deployed to the nodes.
VMs and firmwares etc.
Then create an ngnx server.
You only need to change the runtime in the deployment file.

Release 0.5.0
* Generics Key Brokers (KBS)
* Peer Pods
* ...

![](./Screenshot%202023-04-19%20at%2012.20.39.png)

Q&A
* You need hardware that supports the technologies of TEE
* Performance overheat? Same as Kata containers. The confidential part is not big. Encrypted memory is not an overhead. Do not allow hotplug CPU or Memory. But runtime overhead is low. No benchmarks not available yet. Not for lambdas, rather long running.
* How to move workload from node to node? Not possible without restart.
* Is ARM supported? Not yet


## The Hacker's Guide to Kubernetes - Patrycja Wegrzynowicz, Form3

Top 10 Women in Tech in Poland. 
20+ of XP.
Lead SRE.

Form3 is a financial cloud.
Payment infrastructure via api.
Full remote work model.

K9s Architecture.
Control Plane & Workers (2 Important components).
Control Plane is required for tools like kubectl.
The kubelet of the Worker exposes also.
Unsecured kublet API can be exploited.

OWASP Published a Kubernetes Top 10 in 2022.
1. Insecure Workload Configuration
1. Supply Chain Vulnerabilities
1. Overly Permissive RBAC Configuration
1. Lack of centralized policy enforcement
1. Inadequate Logging and Monitoring
1. Broken authentication mechanisms
1. Missing network segmentation controls
1. Secrets Management Failures
1. Misconfigured Cluster Components
1. Outdated and Vulnerable K8s Components

**DEMO**

https://kubecon.yonlabs.com/sessions/signin

The evil server is in the same subnet as the k8s cluster.
`kubeletctl` is used to shout the perimeter.
Get all pods and filter meta data for container names.
Now scan the pots for RCE or Tokens.

If there is a RCE, establish a reverse shell.
Server establishs the connection to the client using `nc -lvp 4444`.
Sniff HTTP traffic and steal a token.

The kubelet API default configuration is used.
In manage k8s this is not an issue at all.
The writable file system, use read only filesystem.
Container runs as root, do not do that.
Forbid reverse shell tools
Use disto-less images.
Unencrypted traffic in internal networks.
Open egress to the internet.

**DEMO**

Not a root user this time but rw to file system.
But we do a sport scan and find an open port for redis.
Ping redis and check access.
Got access, now scan the table space.
Found stored JWT token.

RCE on a pod in the cluster and so you can effect other workloads.
No network segmentation.
Connection to the redis cluster was possible.
Anonymous access to redis should never be allowed.

Swiss Cheese Security Model
Stacking layer with gaps gives you security as long at least one layer is not aligned on the gaps.
The more layers you have the better.

> A fool with a tool is only a fool.

Continuous Learning is the fundamental paradigm.


## From SBOMs to IBOMs - Know What's Happening in Your Clusters - Ido Neeman, Firefly 

> SBOM: Software Bill of Material

> IBOM: infrastructure Bill of Material

IBOM: full infrastructure inventory.
Their dependencies: like stirage, network, iam.
Child resoources, scale status.
IoC (helm, tf, etc).
3rd party tools, like Datadog, Github...
Configuration & Version.
Ownership.

IBOMS let you assess the entire attack surface of the application.
Understand how app utilize the infra, to find the weak-spot.

Overlooked IBOM.
K8s cluster version.
API version of objects.
Node OS version & type.
DB version | auto upgrade to minor version? -> !.
TF module version? 
Is it public (&vulnerable)?
Consumed infrastructure.
Security Group changes.
Story: Relentless SecOps took production down.
Why does this VPC allows ingress?
Instances from 2017 (still running).
Assumed roles by Saas providers.
Do we still use that SaaS?

SBOM is a compliance darling.

IBOM can also reduce cost is it will help to detect unused resources.

IBOM was neglected by old it.
But they had IBOM: CMDB (Configuration Management Database).
But it's missing for the cloud.

ITSM.
Cloud-Native CMDB.

Helps with drift detection.

Conclusion: xBOM, hot topic but infrastructure was neglected.
Track IBOM (FinOps, compliance).
Understand what's unmanaged.


## Anatomy of a Cloud Security Breach - 7 Deadly Sins - Maya Levine, Sysdig

External cloud assets where more common to breaches.

### 1. Randsomware

Onus, a huge payment service in asia.
Log4sjell with workers name `kworkers` to disguise as k8s resources.
Removed access keys from S3.

Why: The system was not patches quick enough.
The permissions keys where over-permissive.

Take away:
1. Patch as soon as you can.
1. Waiting for a Patch? take other measures.
1. Overly permissive is a boon to attackers.

### 2. Compromised Credentials

Cryptojacking via Compromised Credentials.
Root access used to issue ssh keys to ec2 nodes.
Install manjaro minors.
 
Take Away:
1. Secret Management is crucial
1. Real time monitoring, real-time is the key.


### 3. Poisoned Water

Supply Chain attack in docker images.
AMI with backed in crypto miner.

Motivations: Financial gain, espionage.
DDoS attack sparked with the Ukraine conflict.
Container images where utilized to quickly setup resources.

Take Away: 
1. Trusted Sources only
1. Monitoring to detect malicious behavior.

### 4. Faulty Foundation

Using OSS, might lead to using comprised supply chain.
PyTorch had this issue with the pypy dependency.
`torchtriton 3.0.0` persisted for 3 days.
Did not make it into the stable release.
Blind trust is a bad idea.
The multi-layerd dependencies of modern software makes it really hard to detect.

Take Away: 
* No blind trust.
* Trust but verify. Trust only of you can verify it's behavior. You need dynamic and runtime detection.
* Shift left.

### 5. Credential Theft through Cryptoworms

TeamTNT
* 2019 redis manjaro
* 2021 Dockergeddon
* 2022 Chimaera
* Chimaera 2.0 using AWS Metadata endpoint

Container Escape 'Kiss a dog'
Using encoded python payload.
Due to container running as root.

Take away:
* Do not run container as root.
* Don't Let EC2s initiate New Instances

### 6. Freejacking Abuse

Abusing compute of free tear accounts.
Very sophisticated.

![](./Screenshot%202023-04-19%20at%2016.52.13.png)

Each repo on github had action to run action.
A script was setting up the action.
It also added ssh key for remote access.
With another script post docker commands to the action to mine.
They used open vpn to hide source ips.
Mouse keyboard in0puts.
Captach bypass.
And imap to handle emails.

Each account costed github 15$.

Take Away:
* Free trials at risk.
* Can't rely on solely on malicious IP detection.

### 7. Data Theft

Initial Attack: exploiting public facing app.
Installing crypto miner and also extracting data about the infra.
Next step: enumerate the account further.
Disable cloud trail logs.
Found credentials in terraform state.
Tried to spread to an other account.

Take Away:
* No one should be able to disable cloud trails.
* Terraform access should be very limited.
* Read-only is not safe

Trends:
* Cryptomining will get more popular
* SCALE
* Sophistication of cloud infra attacks
* Supply chain compromises - devastating effects.

How to cope?
* Real time visibility.
* Prioritize: 87% have a high or critical vulnerability - which to tackle first? Tackle the most likely to be exploited.
* Least Permissive: 90% of granted permissions are not used.


## Adopting Network Policies in Highly Secure Environments - Raymond de Jong, Isovalent

eBPF, Cilium, Hubble

Challenges:
* Where to start?
* How to troubleshoot network policies?
* How to stay up-to-date with network policies while the app evolves?
* Hot to prevent app teams to allow every thing?
* How to prove that policies are enforced?

There is no easy road.
There will be trouble when onboarding applications.
Focus on risk reduction.
Define metrics.
Focus on important namespaces and have network monitoring utils.

App Teams & Multi-Tenancy: Focus on namespaces.

![](./Screenshot%202023-04-20%20at%2007.27.35.png)

Key type of risks.
![](./Screenshot%202023-04-20%20at%2007.27.12.png)

Minimize Risks, reduce unused access.

Redice Wide blas radius.
Isolate namespaces.

Measure Risks: Quantify unused access.
Example kube-dns.

Measure Risk: Prioritize.
1. services exposed
1. services exposed accross namesspace
1. services with egress

The cost of overfitting.
Having a policy per service might be to much.
Use global policies as guard rails.

![](./Screenshot%202023-04-20%20at%2007.33.09.png)

Go from coarse to fine-grained policies.

![](./Screenshot%202023-04-20%20at%2007.34.07.png)

Fine graine per namespace

*screenshot*

Manage policies vie CI, e.g. with flux or argo (gitops).
Also can already validate if services to expose wrong ports etc.

eBPF is is for the kernel, what JS is to the browser.
Cilium is build on eBPF.

![](./Screenshot%202023-04-20%20at%2007.34.26.png)

Identity-base security in cilium.
Workloads get a unique identity.
eBPF is used to attach to the data plane.
Cilium supports L3, L4 and L7 security.
Has support gRPC and other protocols.

![](./Screenshot%202023-04-20%20at%2007.37.23.png)

DNS aware network policies for e.g. traffic to s3.

Cluster wide policies

![](./Screenshot%202023-04-20%20at%2007.39.27.png)

For muticluster use-case you can use cilium mesh.
This will allow for cluster-aware policies.
The cluster lean each others cilicum identities.

![](./Screenshot%202023-04-20%20at%2007.40.39.png)

Trouble shooting with Hubble.
Hubble consists of UI, CLI and Metrics.
Can visualize service to service communication, protocols and ports.
There is a network policy editor which is very nice to create network policies.
They provide cilium grafana dashboards.

**DEMO**

Shows a hubble ui.
Live flows can be inspected.
We want to secure the name space.
Apply a network policy to only allow access to the dns to see which targets are talked to.
Hubble show exactly which dns are accessed.
Now new policies can be created for this access.
Also the grafan dashboard show this matching.
Next policy is L7 to allow port 80 and https.
We see in hubble that the server allows all traffic on port 80.
Currently it allows all methods.
Next secure the client.
Allow egress to 80 and allows the DNS we saw before.
In grafana we can see that all traffic is matched and we can remove the default allow policy of the namespace.

What to do if the introduce a new app or namespace?
Here a new app is introduced.
There will be drops in hubble because the other namespace is not allowed.
In grafana we see that the policy verdict show up as not allowed.
So we adjust the policies of the server.
And the other app can now access the server.

