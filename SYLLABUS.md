# Master DevOps Architect Syllabus

Basics se Architect level tak, 7 modules. Har sub-topic `/complete` ke baad `[x]` mark hoga.

## Module 0: Git & GitHub for DevOps Architects (Essentials only)
- [ ] **0.1 Core Ops, SSH & PATs:** init/clone/add/commit/push/pull, remotes, SSH keys vs fine-grained PATs.
- [ ] **0.2 Branching, PRs, Tags & Conflicts:** branch strategies, Pull Requests, tags/releases, merge conflict resolution.
- [ ] **0.3 Incident Recovery, Revert & Secrets Cleanup:** `revert` vs `reset`, `reflog` recovery, leaked secrets cleanup.

## Module 1: DevOps Scripting
- [ ] **1.1 YAML:** syntax, data types, anchors/aliases, multi-doc files, common indentation traps.
- [ ] **1.2 Bash & CLI Text Tools:** variables, loops, functions, exit codes, `set -euo pipefail`, `grep`/`sed`/`awk`/`jq`.
- [ ] **1.3 Python for DevOps & Cloud SDKs:** `subprocess`, files/JSON/YAML, `requests`, boto3 / Azure SDK / Google Cloud SDK.
- [ ] **1.4 PowerShell for DevOps & Azure:** objects & pipeline, modules, error handling, Az PowerShell module.
- [ ] **1.5 Scripting Failures:** silent failures, quoting/word-splitting bugs, CRLF issues, dependency & auth errors.

## Module 2: Linux Internals & Docker
- [ ] **2.1 Basics & Architecture:** `dockerd`, `containerd`, `containerd-shim`, `runc`, OCI specs.
- [ ] **2.2 Dockerfile:** instructions, layer caching, `ENTRYPOINT` vs `CMD`, non-root `USER`, PID 1.
- [ ] **2.3 Multi-stage Builds & BuildKit:** multi-stage, cache/secret mounts, distroless/scratch images.
- [ ] **2.4 OverlayFS & Volumes:** lowerdir/upperdir/merged, Copy-on-Write, volumes vs bind mounts vs `tmpfs`.
- [ ] **2.5 Networking:** `bridge`, `host`, `none`, `overlay`, `macvlan`, `iptables` NAT, DNS, MTU.
- [ ] **2.6 Kernel Namespaces, cgroups, Trivy & Cosign:** namespaces, cgroups v1/v2, capabilities, CVE scanning, image signing.
- [ ] **2.7 Compose & Docker Failures:** Compose healthchecks/depends_on, `OOMKilled` (137), SIGTERM (143), disk full, `exec format error`.

## Module 3: CI/CD Engineering
- [ ] **3.1 CI/CD Architecture Comparison:** Jenkins vs GitLab CI vs Azure DevOps.
- [ ] **3.2 Jenkins Basics & Pipelines:** controller/agent, `JENKINS_HOME`, Declarative vs Scripted pipelines.
- [ ] **3.3 Jenkins Shared Libraries, K8s Agents & JCasC:** `vars/`/`src/`, dynamic Kubernetes agents, Configuration as Code.
- [ ] **3.4 GitLab CI/CD & Runners:** `.gitlab-ci.yml`, stages, `needs`, `rules`, artifacts vs cache, runner executors.
- [ ] **3.5 Azure DevOps Pipelines, Agents & Workload Identity:** YAML pipelines, templates, environments/approvals, self-hosted agents, Workload Identity service connections.
- [ ] **3.6 Multi-Tool End-to-End Project:** one app built, scanned, signed and deployed to Kubernetes via Jenkins, GitLab CI and Azure DevOps.
- [ ] **3.7 CI/CD Failures:** stuck executors, runner OOM/socket errors, expired service connections, queue bottlenecks.

## Module 4: Kubernetes & Scratch On-Prem Setup on GCP VMs
- [ ] **4.1 Control Plane & Worker Internals:** `kube-apiserver`, `etcd`, scheduler, controller-manager, `kubelet`, `kube-proxy`, `containerd`.
- [ ] **4.2 Scratch kubeadm Cluster on 3 GCP VMs:** 1 control plane + 2 workers, `kubeadm init/join`, Calico/Cilium CNI, MetalLB.
- [ ] **4.3 Workloads:** Pods, init/sidecar containers, Deployments, StatefulSets, DaemonSets, Jobs/CronJobs.
- [ ] **4.4 Probes, QoS & Scheduling:** liveness/readiness/startup, requests/limits, QoS classes, affinity, taints/tolerations, PDBs.
- [ ] **4.5 ConfigMaps, Secrets & ESO:** ConfigMaps, Secrets, etcd encryption at rest, External Secrets Operator.
- [ ] **4.6 Networking, CoreDNS, Gateway API & NetworkPolicies:** Services, EndpointSlices, CoreDNS (`ndots:5`), Ingress vs Gateway API, NetworkPolicies.
- [ ] **4.7 Storage & CSI:** PV/PVC, StorageClass, access modes, reclaim policies, on-prem vs cloud CSI.
- [ ] **4.8 RBAC, PSS, Webhooks, Kyverno & Falco:** ServiceAccounts, RBAC, Pod Security Standards, admission webhooks, Kyverno, Falco.
- [ ] **4.9 HPA, KEDA, Helm, Kustomize & ArgoCD:** autoscaling, Helm charts, Kustomize overlays, GitOps with ArgoCD.
- [ ] **4.10 K8s Production Failures:** `CrashLoopBackOff`, `ImagePullBackOff`, `Pending`, `NodeNotReady`, PVC stuck, broken webhooks, expired certs, etcd quorum loss.

## Module 5: Managed K8s & Cloud Architecture
- [ ] **5.1 GKE:** Standard vs Autopilot, VPC-native networking, Workload Identity, node pools.
- [ ] **5.2 AWS EKS:** VPC CNI, IRSA / Pod Identity, managed node groups, Karpenter, ALB controller.
- [ ] **5.3 Azure AKS:** Azure CNI, Entra Workload ID, node pools, AGIC / Application Gateway for Containers.
- [ ] **5.4 Multi-Cloud Drills:** cross-cloud failures, IAM/networking misconfigurations, cost & quota gotchas.

## Module 6: Production Observability & Monitoring
- [ ] **6.1 Pillars, RED & USE:** metrics, logs, traces, SLIs/SLOs, RED and USE methods.
- [ ] **6.2 Prometheus & Thanos:** scraping, PromQL, recording rules, long-term storage with Thanos.
- [ ] **6.3 Grafana & Alertmanager:** dashboards, alert rules, routing, silencing, inhibition.
- [ ] **6.4 Fluent Bit, Loki, EFK, OpenTelemetry & Tempo:** log pipelines, OTel Collector, distributed tracing.
- [ ] **6.5 CI/CD & Cloud Monitoring:** pipeline metrics, CloudWatch, Azure Monitor, Google Cloud Monitoring.
- [ ] **6.6 Monitoring Failures:** missing metrics, cardinality explosions, alert fatigue, dropped logs, broken traces.
