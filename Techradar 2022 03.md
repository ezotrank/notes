# Techradar 2022/03

tags: #techradar

Link: https://www.thoughtworks.com/content/dam/thoughtworks/documents/radar/2022/03/tr_technology_radar_vol_26_en.pdf

## Technologies


### Four key metrics

Key metrics as defined by the DORA research program:

- Change lead time
- Deployment frequency
- Mean time to restore (MTTR)
- Change fail percentage

Links:
- [Google Cloud DevOps](https://cloud.google.com/devops/)
- [DORA quick check](https://www.devops-research.com/quickcheck.html)
- [Explore DORA's research program](https://www.devops-research.com/research.html)


### Definition of production readiness

In an organization that practices the “you build it, you run it” principle, a definition of production readiness (DPR) is a useful technique to support teams in assessing and preparing the operational readiness of new services.

Links:
- [Google’s concept of a production readiness review (PRR)](https://sre.google/sre-book/evolving-sre-engagement-model/#:%7E:text=The%20most%20typical,of%20a%20service)


### Documentation quadrants

Links:
- [Documentation quadrants](https://documentation.divio.com)


### Rethinking remote standups

Links:
- [Stand-Up Meetings Are Dead (and What to Do Instead)](https://www.honeycomb.io/blog/standup-meetings-are-dead/)


### Server-driven UI

Server-driven UI separates the rendering into a generic container in the mobile app while the structure and data for each view
is provided by the server. 


### Software Bill of Materials

With continued pressure to keep systems secure and no reduction in the general threat landscape, a machine-readable Software Bill of Materials (SBOM) may help teams stay on top of security problems in the libraries that they rely on.

Links:
- [Syft](https://github.com/anchore/syft)


### Tactical forking

Tactical forking is a technique that can assist with restructuring or migrating from monolithic codebases to microservices.

Links:
- [Tactical forking](https://faustodelatog.wordpress.com/2020/10/16/tactical-forking/)


### Team cognitive load

A system’s architecture mimics an organizational structure and its communication. It’s not big news that we should be intentional about how teams interact — see, for instance, the Inverse Conway Maneuver

Links:
- [Team Topologies - by Matthew Skelton and Manuel Pais](https://teamtopologies.com/book)
- [Team Cognitive Load Assessment](https://github.com/TeamTopologies/Team-Cognitive-Load-Assessment)


### Transitional architecture

A transitional architecture is a useful practice used when replacing legacy systems.
Thus they help with avoiding the trap of defaulting to a “big bang” legacy replacement approach, because you cannot make smaller interim steps line up with a final architectural vision.

Links:
- [Transitional Architecture](https://martinfowler.com/articles/patterns-legacy-displacement/transitional-architecture.html)


### CUPID

He argues that instead of sticking to a set of rules like SOLID, using a set of properties to aim for is more generally applicable. He came up with what he calls the CUPID properties to describe what we should strive for to achieve “joyful” code: Code should be composable, follow the Unix philosophy and be predictable, idiomatic and domain based.

Links:
- [CUPID—for joyful coding](https://dannorth.net/2022/02/10/cupid-for-joyful-coding/)


###  Operator pattern for nonclustered resources

Links:
- [Operators](https://cloud.redhat.com/learn/topics/operators)
- [Argo CD](https://thoughtworks.com/radar/platforms/argo-cd)


### Service mesh without sidecar

Service mesh is usually implemented as a reverse-proxy process, aka sidecar, deployed alongside each service instance. Although these sidecars are lightweight processes, the overall cost and operational complexity of adopting service mesh increases with every new instance of the service requiring another sidecar.

Links:
- [Cilium service mesh](https://github.com/cilium/cilium-service-mesh-beta)


### SLSA

As software continues to grow in complexity, the threat vector of software dependencies becomes increasingly challenging to guard against.
Supply chain Levels for Software Artifacts, or SLSA (pronounced “salsa”), is a consortium-curated set of guidance for organizations to protect against supply chain attacks, evolved from internal guidance Google has been using for years.

Links:
- [slsa.dev](https://slsa.dev)


### The streaming data warehouse

The need to respond quickly to customer insights has driven increasing adoption of event-driven architectures and stream processing.
Standardizing on SQL as the universal streaming language lowers the barrier for implementing streaming data applications. Tools like ksqlDB and Materialize help transform these separate applications into unified platforms. 

Links:
- [ksqlDB](https://www.thoughtworks.com/radar/languages-and-frameworks/ksqldb)


### Holds

**Miscellaneous platform teams** 

**Production data in test environments** 
Fake data is a safer approach, and tools exist to help in its creation. We do recognize there are reasons for specific elements of production data to be copied, for example, in the reproduction of bugs or for training of specific ML models. Here our advice is to proceed with caution.

**SPA by default**
Indeed, we’ve started to notice that many newer developers aren’t even aware of
an alternative approach, as they’ve spent their entire career in a framework like React. We believe that many websites will benefit from the simplicity of server-side logic, and we’re encouraged by techniques like Hotwire that help close the gap on user experience.


## Platforms


### CircleCI

The wide variety of executor types provides flexibility to set up jobs in Docker, Linux, macOS or Windows VMs.

Links:
- [CircleCI](http://circleci.com/)


### Couchbase

Among the additions to the product suite are Couchbase Mobile and the Couchbase Sync Gateway. These features work together to keep persistent data on edge devices up-to-date even when the device
is offline for periods of time due to intermittent connectivity.


### eBPF

Links:
- [Isto](https://thoughtworks.com/radar/platforms/istio)
- [Bumblebee](https://github.com/solo-io/bumblebee)
- [Cilium](https://thoughtworks.com/radar/tools/cilium)


### GitHub Actions

Links:
- [GitHub Actions Security Guide](https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions)
- [act](https://github.com/nektos/act)


### Reusable workflows in Github Actions

Links:
- [Reusing Workflow](https://docs.github.com/en/actions/using-workflows/reusing-workflows)

### Sealed Secrets

Kubernetes natively supports a key-value object known as a secret. However, by default, Kubernetes secrets aren’t really secret. They’re handled separately from other key-value data
so that precautions or access control can be applied separately. There is support for encrypting secrets before they are stored in etcd, but the secrets start out as plain text fields in configuration files.

Links:
- [Sealed Secrets](https://github.com/bitnami-labs/sealed-secrets)


### actions-runner-controller

actions-runner-controller is a Kubernetes controller that operates self-hosted runners for GitHub Actions on your Kubernetes cluster. With this tool you create a runner resource on Kubernetes, and it will run and operate the self-hosted runner. 

Links:
- [actions-runner-controller](https://github.com/actions-runner-controller/actions-runner-controller)

### Colima 

Colima is becoming a popular open alternative to Docker for Desktop. It provisions the Docker container runtime in a Lima VM, configures the Docker CLI on macOS and handles port-forwarding and volume mounts

### CycloneDX

CycloneDX is a standard for describing a machine-readable Software Bill of Materials (SBOM).
As software and compute fabrics increase in complexity, software becomes harder to define. Originating with OWASP, CycloneDX improves on the older SPDX standard with a broader definition that extends beyond the local machine dependencies to include runtime service dependencies.

### Temporal

Temporal is a platform for developing long-running workflows, particularly for microservice architectures. 


## Tools


### tfsec

For our projects using Terraform, tfsec has quickly become a default static analysis tool to detect potential security risks.

### AKHQ

AKHQ is a GUI for Apache Kafka that lets you manage topics, topics data, consumer groups and more.

### kube-score

kube-score is a tool that does static code analysis of your Kubernetes object definitions. The output is a list of recommendations for what you can improve to make your application more secure and resilient

### Podman

As an alternative to Docker, Podman has been validated by many of our teams. Podman introduces
a daemonless engine for managing and running containers which is an interesting approach in
comparison to what Docker does


### Excalidraw

Excalidraw is a simple but powerful online drawing tool that our teams enjoy using.

### GoReleaser

GoReleaser is a tool that automates the process of building and releasing a Go project for different
architectures via multiple repositories and channels, a common need for Go projects targeting
different platforms.

### Grype

Securing the software supply chain has become a commonplace concern among delivery teams,
a concern that is reflected by the growing number of new tools in this space.

### Infracost

One often-cited advantage of moving to the cloud is transparency around infrastructure spend. In
our experience, this is often not the case. 

### jc

In our previous Radar, we placed modern Unix commands in Assess. One of the commands featured
in that collection of tools was jq, effectively a sed for JSON. jc performs a related task: it takes the
output of common Unix commands and parses the output into JSON.

### skopeo

skopeo is a command line utility that performs various operations on container images and image
repositories. It doesn’t require a user to be root to do most of its operations nor does it require a
daemon to be running. It’s a useful part of a CI pipeline; we’ve used it to copy images from one registry
to another as we promote the images.

### SQLFluff

While linting is an ancient practice in the software world, it’s had slower adoption in the data world.
SQLFluff is a cross-dialect SQL linter written in Python that ships with a simple command line
interface (CLI), making it easy to incorporate into a CI/CD pipeline.


## Languages and Frameworks


### SpiceDB

SpiceDB is a database system, inspired by Google’s Zanzibar, for managing application permissions.


### sqlc

sqlc is a compiler that generates type-safe idiomatic Go code from SQL.

