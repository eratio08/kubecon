# Day 3

## Keynote: Opening Remarks

--

## Sponsored Keynote: Data Protection and Application Recovery in Cloud and Kubernetes - Petter Sveum, Senior Distinguished Engineer and Chief Architect, Veritas

Realities:
* More and more critical infra is build in K8s 
* 55% orgs are using K8s
* 90% will run in 2026

More people will move into the cloud like banks etc, they need persistent storage, data protections and disaster recovery.

Vision: Autonomous Data Management.

![](./Screenshot%202023-04-21%20at%2009.07.28.png)

What would this look like?

![](./Screenshot%202023-04-21%20at%2009.08.47.png)

Veritas build this for k8s.


## Keynote: Trust No System: The Unsettling Reality of Zero Trust - Frederick Kautz, Steering Committee Member, SPIFFE/SPIRE

What our goal with security:
* C
* I
* A

This isn't about security: It's about Trust.
Like trust in the banking system.
What happens if trust eroded?
Establish enough trust in a system to run the task.
All QA, all testing is just to build trust.

What do we mean when we say trust?
Trust is not a single thing you can build.
Trust is build from certain properties.
It's not a property it's an assessment.

> Dorothy E. Denning

She challenged the US National Standard on how to build a trusted system.

Trust is a decision!

> Confidential Computing Consortium

Trust also as a context.
And it has a time frame.
It's also asymmetrical: bank to me vs. me to the bank.

Too much trust: 1985-1987 Therac-25, nuclear issue.
Too little trust: a SIEM alert was not trust and attack could continua.

Trust Framework, also very contextual.
> Book: Trust in Computer System in the Cloud

Start with the basics:
* Patch management
* User account management
* Awareness programs

Next:
* Develop a framework that explicitly reason about trust.
* Build a culture around asking what you are trusting.
* Ask what happens if that trust is violated. (Consequences, Blast Radius)

What about zero trust?
Actually zero IMPLICIT trust.
Only explicit trust.


## Sponsored Keynote: Achieving Kubernetes Nirvana with Platforms, People & Processes - Denise Schannon, Sr. Director of Engineering, Rancher by SUSE

History:
* K8s, 9 years, v1.27
* Rancher 8 years

Making software extensible:
* Remove dependencies
* Add features to extend into you software

The perfect team does not exist.
Continuously review your team needs.
What are the needs of individual engineers, company?
Adjust & Adapt & Repeat.
 
They use Kanban.
Engineers can decide where they want to become a subject matter expert.


## Keynote: Enabling Real-Time Media in Kubernetes - Giles Heron, Principal Engineer, Cisco

Media Streaming match project.
Mass real-time streaming at a good cost point.

Taxonomy

![](./Screenshot%202023-04-21%20at%2009.32.47.png)

K8s more in the web app quarter.
Live Media is in the opposite order.
The is no time in the video stream because of 3-=40 seconds delay.

Live Video Distribution Chain.

![](./Screenshot%202023-04-21%20at%2009.34.52.png)

How does internet streaming today?
Https/TCP Requests.
Latency vs Reliability.

RTSP - TCP dest port 554.
The UDP used later on as some issues.

IP Multi-cast.

![](./Screenshot%202023-04-21%20at%2009.41.11.png)

Demo setup

![](./Screenshot%202023-04-21%20at%2009.43.43.png)

Benefits:
* Obersvability
* Security
* Distribution
* Deployability


## Sponsored Keynote: Cloud Native 2.0: Uplift Productivity with Openness and Innovation - Bill Ren, Chief Open Source Liaison Officer, Huawei

Challenges:
* Most software is not in the cloud yet
* Huge cap between cloud native & traditional industry

Kuasar: Efficient Multi-Sanbox Container Runtime.

![](./Screenshot%202023-04-21%20at%2009.52.03.png)


## Keynote: Is Kubernetes Delivering on its Promise? A Platform Engineering Perspective - Aparna Subramanian, Director of Production Engineering, Shopify

> End Users: (CNCF lingo) user that user cloud native but do not sell cloud native product.

Why do we need platforms?
Stakeholders:

![](./Screenshot%202023-04-21%20at%2009.57.07.png)

What it takes to build a platform:

Old way:

![](./Screenshot%202023-04-21%20at%2009.58.51.png)

K8s today

![](./Screenshot%202023-04-21%20at%2010.00.03.png)

Platform as a Service for Developers.

K8s:
* Portability: 5 Stars
* Reliability: 5 Stars
* Extensibility: 5 Stars
* Scalability: 3 Stars
* Simplicity: 1 Start

Issues:
* Yaml complexity
* Painful k8s upgrades
* Multi-Cluster management

Options for building a platform:

![](./Screenshot%202023-04-21%20at%2010.04.19.png)


## Keynote: Top End User Award

Mercedes Benz


## Keynote: Closing Remarks

EU Cyber Resilience Act.
A lot of rules that might impact OSS maintainers, foundations and even package management.


## Prevent Embarrassing Cluster Takeovers with This One Simple Trick! - Daniele de Araujo dos Santos & Shane Lawrence, Shopify

Foot Guns with K8s security.

`kubeaudit`

53% security issues due to k8s misconfiguration in the last 12 month (redhati state of security report).
Misconfiguration is a top concern.

Azurescape.
Cross account takeover, due to a conainer escape.
How?
two-year old CVE in runC.
RCE on the api-server.
Leading to run of custom containers.

It required root access from the container.
So it could have been prevented by using k8s security context.

Security Control

![](./Screenshot%202023-04-21%20at%2011.42.43.png)

`kubeaudit` oss tool.

> kubernetes goat, resources to learn k8s security

> we should try `kubeaudit`

Principles

![](./Screenshot%202023-04-21%20at%2011.58.49.png)

`kubeaudit autofix -f test.yml`

**DEMO**

Image magic lib and it's prone to RCE of images contain scripts.
Set the hots filesystem access to read-only.

Using host networks allow to bypass network security policies.
Now you can get token from the metadata service.
Use the token to access a block storage.
Stripping the hostNetwork so the pod token identity is accessible, which can not access toke store.

To take over the whole cluster we need to use a privileged container.
NGINX is running as root.
Here also use host PID, share pid space of host, but also would work without.
Escape the container and escape into the host namespace.
Now you are root on the host.
Add custom ssh keys.
Enumerate the containers.
Get the token of the kube system container.
Replace apps image with custom image, this effects any replica.

Again kubeaudit autofix
Set security context `privileged: false`, `runAsNotRoot: true.

There is no simple trick!
Shifting left: snyk, trivy, anchor.
Code scanning: sast, kubeaudit.

SARIF report with kubeaudit for CI.

> MITRE ATT@ACK Freamework

![](./Screenshot%202023-04-21%20at%2012.00.40.png)

You might use it on helm by using the dry run e.g.


## Least Privilege Containers: Keeping a Bad Day from Getting Worse - Greg Castle & Vinayak Goyal, Google

![](./Screenshot%202023-04-21%20at%2012.07.46.png)

Every linux kernel has a live breakout, right now.
In 2022 17 exploitable breakout.

How to run as non root?

![](./Screenshot%202023-04-21%20at%2012.08.37.png)

rootlesscontaine.rs (this is about the runtime not running as root)

1. Modify container to function as non-root
1. ? (missed this one)

How to fix containers expecting root.
Make new docker file and fix all permissions `chown -R ...`.
Hard work because you need to understand the whole container workflow.

How to do a platform-wide migration to non root?
* Block new root containers.
* Exempt and migrate existing root containers: fix upstream if possible.

Root pre-submit check.
On the source code.

Modify the pod-spect and test.

Design Choices:
* In container vs runtime configuration.
* Enforcement/Auditability

If you own the container in container is great.
If you do not own the container use configuration.

![](./Screenshot%202023-04-21%20at%2012.09.50.png)

Enforcement/Auditability.
Use gatekeeper

![](./Screenshot%202023-04-21%20at%2012.10.49.png)

UID/GID, no collision on the host.

![](./Screenshot%202023-04-21%20at%2012.15.20.png)

Challenges & Solutions:
* Access to things on the host
* Capabilities

Host files access

![](./Screenshot%202023-04-21%20at%2012.16.22.png)

E.g. is a socket needs to be created.
You could use `fsGroup`, but does not work for host files, is working for emptyDir.
You could use init containers, and they can run as root.
This approach will work if container access a single file
But wont work if multiple containers need access to the same file.
`supplementalGroups` can work here.

Capabilities management.
Drop all and only grant what you need.

![](./Screenshot%202023-04-21%20at%2012.17.39.png)

Always set `allowPrivilegeEscalation: false`.

![](./Screenshot%202023-04-21%20at%2012.18.11.png)

Use setcap in the dockerfile.

![](./Screenshot%202023-04-21%20at%2012.19.52.png)

It seems harder than it should be.

Linux `user_namespaces`, should properly isolate container root from host root.

![](./Screenshot%202023-04-21%20at%2012.23.18.png)

Will only work for stateless ports.

hostUsers FTW

![](./Screenshot%202023-04-21%20at%2012.24.34.png)

Takeaways:
* Huge security value from running as non-root
* org-wide conversation
* help is coming: `hostUsers`

![](./Screenshot%202023-04-21%20at%2012.27.05.png)


## Malicious Compliance: Reflections on Trusting Container Scanners - Ian Coldwater, Independent; Duffie Cooley, Isovalent; Brad Geesaman, Ghost Security; Rory McCune, Datadog

k8s.rip/demo-base

`docker scan` -> `docker scout`

`FROM composer`

* Trivy 
* Grype 
* docker scan 
* docker scoute

![](./Screenshot%202023-04-21%20at%2014.07.48.png)

Scanner will use package detection.
Might not work for not wide spread managers/distos.
It will check dependency files.
Binary medatada is also scanned.

![](./Screenshot%202023-04-21%20at%2014.09.50.png)

Fixing things is hard.
Could break production of it's impossible due to vendor image.

Malicious compliance.
How to obscure this to hide from the scanners.

![](./Screenshot%202023-04-21%20at%2014.13.00.png)

This will hide close to call findings from the docker scanners.
Now we could remove package metadata.

![](./Screenshot%202023-04-21%20at%2014.14.40.png)

All OS vulnerabilities are gone now.
So get rid of dependency detection.
Use symlinks to confuse the scanners.

![](./Screenshot%202023-04-21%20at%2014.16.49.png)

Now all dependency detection are gone.
How to get rid of the binary detection.
UPX packing to obfuscate the binary.

![](./Screenshot%202023-04-21%20at%2014.19.37.png)

Stil some findings.
This might be due to the layers.
Use multi layer build to get rid of these.

```Dockerfile
FROM scratch
COPY --from=build / .
```

To get rid of layers.

**SBOM**
Create an sbom and scan the sboms.
`Trivy, Syft` to generate SBOM.

SBOM is compliance but it's not secure.
Scanning the SBOM did to detect the issues.
The SBOM formats are non standard.
Very inconsistent results.

![](./Screenshot%202023-04-21%20at%2014.38.07.png)


## Building SLSA 3 Conforment Attestors for Artifacts Generated on GitHub - Ian Lewis & Asra Ali, Google

Software Delivery pipelines consists of resources and processes.
A long the way there are many attack vectors.process

![](./Screenshot%202023-04-21%20at%2017.41.38.png)

SALA framework to secure this pipeline

![](./Screenshot%202023-04-21%20at%2017.42.32.png)

Attestation: proof of an event.
* Code Scanning
* Repo scanning
* Build provenance (slsa)
* SBOM
* VEX

SBOM Attestation.

![](./Screenshot%202023-04-21%20at%2017.44.25.png)

Trustworthy Supply chain metadata.
Attestation require trust:
* Integrity
* Authentic non forgeable: can not be influenced by users

SLSA Level 3 provenance.

How to build an attestor.
What do they to?
They attest to something that happened.
Attesting that some artifact was created.
The attestor needs to be isolated from the event.
Cannot be impersonated.

Problems:
* What if the build platform can not attest to the builds
* The build platform be decoupled

Attestrors: General Framework

![](./Screenshot%202023-04-21%20at%2017.50.10.png)

Use the available primitives.
Build in a secured VM.
Pass artifact digest to Provenance.
There musst be an unmodifyable way to pass outputs to inputs.

Provenance:
* Record trusted system prams (envs)
* Record external params (inputs)
* Records artifact digest

Sign:
* Sign the recorded data, signal trusted provenance
* OIDC of github can be used for signing certs.

Verification:
* Establish trust (by verification)

![](./Screenshot%202023-04-21%20at%2017.55.33.png)

Use the verification for policy engines.

Container based attestor.

![](./Screenshot%202023-04-21%20at%2018.01.09.png)

Limitation: build inside a container.
So scanner would need to be included as well.

Delegated Attestor Framework.

![](./Screenshot%202023-04-21%20at%2018.07.20.png)

It enables existing 3rd party tools to provide attestors.
No need to understand SLSA.
Low overhead to integrate.
You would use the tool authors attestors.
Trust between tool writers & users.

e.g. Node.js/npm attestor.
Provenance is published along side the package to npm.
Provenance is attached as metadata of the package.
Provenance also shown in NPM.

![](./Screenshot%202023-04-21%20at%2018.12.36.png)


## Future of Service Mesh - Sidecar or Sidecarless or Proxyless? - Idit Levine & Yuval Kohavi, Solo.io; Keith Mattix II, Microsoft; Eric Van Norman, IBM; John Howard, Google

There is a new approach that will work without a side car.
The new approach will be on a node level.


## Can You Keep a Secret? on Secret Management in Kubernetes - Liav Yona & Gal Cohen, Firefly



