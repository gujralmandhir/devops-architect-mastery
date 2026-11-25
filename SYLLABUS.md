# Master DevOps Architect Syllabus

## Module 0: Git & GitHub for DevOps (Production Workflows)
- [ ] **0.1 Git Internals:** `.git` directory, blobs, trees, commits, HEAD, staging area, `git reflog`.
- [ ] **0.2 Branching Strategies:** GitFlow vs GitHub Flow vs Trunk-Based Development (CI/CD ke liye best practice).
- [ ] **0.3 Merge, Rebase & Conflict Resolution:** Fast-forward vs 3-way merge, interactive rebase (`rebase -i`), cherry-pick, merge conflicts resolve karna.
- [ ] **0.4 GitHub DevOps Features:** Pull Requests, CODEOWNERS, Branch Protection Rules, SSH keys vs Fine-grained PATs, Webhooks, GitHub Secrets.
- [ ] **0.5 Real-World Git Disasters:** Force-push recovery via `reflog`, detached HEAD fix, accidentally committed secrets cleanup (`git filter-repo`), broken rebase recovery.

## Module 1: Linux Internals & Docker (Basics to Internals)
- [ ] **1.1 Docker Architecture:** `dockerd`, `containerd`, `containerd-shim`, `runc`, OCI specs.
- [ ] **1.2 Kernel Isolation:** Linux Namespaces (`pid`, `net`, `mnt`, `uts`, `ipc`, `user`), `cgroups v1/v2`, `seccomp`, `AppArmor`, Capabilities.
- [ ] **1.3 Storage & Layers:** `OverlayFS2` (lowerdir/upperdir/merged), Copy-on-Write, Volumes vs Bind Mounts vs `tmpfs`.
- [ ] **1.4 Dockerfile & BuildKit:** Multi-stage builds, layer caching, secret mounts, distroless/scratch, non-root `USER`, `ENTRYPOINT` vs `CMD`, PID 1 (`tini`).
- [ ] **1.5 Docker Networking:** `bridge` (default vs user-defined DNS), `host`, `none`, `overlay` (VXLAN), `macvlan`, `iptables` NAT, MTU issues.
- [ ] **1.6 Compose & Supply Chain Security:** Healthchecks, logging drivers, rootless Docker, Trivy CVE scanning, Cosign image signing.
- [ ] **1.7 Docker Production Failures:** `OOMKilled` (137), `SIGTERM` ignored (143), orphan volume disk full, custom DNS failure, `exec format error`.

## Module 2: Complete CI/CD Engineering (Jenkins, GitLab CI & Azure DevOps)
- [ ] **2.1 CI/CD Architecture Comparison:** Jenkins (Controller/Agent) vs GitLab CI (Server + Runners) vs Azure DevOps (Pipelines + Agents).
- [ ] **2.2 Jenkins Deep Dive:** `JENKINS_HOME`, Declarative vs Scripted Pipelines, Groovy Shared Libraries (`vars/`, `src/`), CPS & `NotSerializableException`, JCasC.
- [ ] **2.3 Jenkins Dynamic Agents & Security:** Docker-in-Docker vs Kaniko/Buildah on K8s, RBAC, Credentials/Vault, Webhooks & CSRF crumbs.
- [ ] **2.4 GitLab CI/CD Complete:** `.gitlab-ci.yml`, Stages, Jobs, `needs` (DAG), Artifacts vs Cache, `rules`, Child/Parent & Multi-project pipelines, GitLab Container Registry.
- [ ] **2.5 GitLab Runners Architecture:** Executors (Shell, Docker, Kubernetes), autoscaling runners, OIDC cloud auth.
- [ ] **2.6 Azure DevOps (ADO) Complete:** ADO Org/Projects, Azure Repos, Azure Pipelines YAML (`stages`, `jobs`, `steps`, `templates`, `variable groups`, `environments` & approvals), Self-hosted VMSS/AKS agents, Workload Identity Service Connections.
- [ ] **2.7 End-to-End Multi-Tool CI/CD Project:** Ek app ko Jenkins, GitLab CI, aur Azure DevOps teeno se build, Trivy scan, sign, aur Kubernetes par deploy karna (ArgoCD GitOps).
- [ ] **2.8 Real-World CI/CD Failures:** Jenkins deadlocked executors & `NotSerializableException`, GitLab Runner `oom_killed` / socket errors, ADO Service Connection token expiry & queue bottlenecks.

## Module 3: Kubernetes Architecture & Scratch On-Premises Setup (GCP VMs)
- [ ] **3.1 Control Plane Internals:** `kube-apiserver` (authN/authZ/admission), `etcd` (Raft, MVCC, backup/restore, defrag), `kube-scheduler`, `kube-controller-manager`.
- [ ] **3.2 Worker Node Internals:** `kubelet` (CRI, CNI, CSI, static pods, PLEG), `kube-proxy` (`iptables` vs `IPVS` vs `eBPF`), `containerd` & pause container.
- [ ] **3.3 Scratch On-Prem K8s Cluster on GCP VMs (`kubeadm`):** 3 GCP VMs (1 Control Plane + 2 Workers) par scratch se `kubeadm init/join`, `containerd`, **Calico/Cilium CNI**, aur **MetalLB** setup karna.
- [ ] **3.4 Core Workloads & Pod Patterns:** Pods, Init/Sidecar/Ambassador/Ephemeral debug containers, Deployments, StatefulSets (Headless services), DaemonSets, Jobs/CronJobs.
- [ ] **3.5 Scheduling, Probes & QoS:** `liveness`/`readiness`/`startup` probes, `requests`/`limits`, QoS (`Guaranteed`, `Burstable`, `BestEffort`), Affinity/Anti-Affinity, Taints/Tolerations, `TopologySpreadConstraints`, PDBs.
- [ ] **3.6 Configuration & Secrets:** ConfigMaps, Secrets, volume hot-reload, `etcd` encryption at rest, External Secrets Operator, Sealed Secrets.
- [ ] **3.7 Networking Deep Dive:** Pod-to-Pod packet flow, Services (`ClusterIP`, `NodePort`, `LoadBalancer`, `Headless`), `EndpointSlices`, CoreDNS (`ndots:5` trap), NGINX Ingress vs Gateway API, `NetworkPolicies`.
- [ ] **3.8 Storage & CSI:** PV, PVC, `StorageClass`, Access Modes (`RWO`, `ROX`, `RWX`), Reclaim Policies, On-Prem NFS/Longhorn vs Cloud CSI, VolumeSnapshots.
- [ ] **3.9 Security & Governance:** X.509 certs, `kubeconfig`, ServiceAccounts, RBAC, Pod Security Standards, Admission Webhooks, Kyverno/OPA Gatekeeper, Falco, Audit logs.
- [ ] **3.10 Autoscaling, Helm, Kustomize & GitOps:** HPA, VPA, KEDA, Helm charts, Kustomize overlays, ArgoCD GitOps, `kubeadm` cluster upgrades.
- [ ] **3.11 Real-World K8s Production Failures:** `CrashLoopBackOff`, `ImagePullBackOff`, `CreateContainerConfigError`, `Pending` pods, `Evicted` pods, `NodeNotReady` / PLEG unhealthy, CoreDNS `ndots` throttling, PVC `Multi-Attach` / `Terminating` stuck, broken `ValidatingWebhook`, expired certs, `etcd` quorum loss.

## Module 4: Managed Kubernetes & Cloud Architecture (GCP, AWS, Azure)
- [ ] **4.1 GKE (Google Kubernetes Engine):** Standard vs Autopilot, VPC-native alias IPs, Workload Identity Federation, Cloud Load Balancing (NEGs), PD/Filestore CSI, Node Auto-Provisioning.
- [ ] **4.2 AWS EKS:** Control plane, AWS VPC CNI (IP exhaustion & prefix delegation), IRSA & EKS Pod Identity, AWS Load Balancer Controller (ALB/NLB), EBS/EFS CSI, Karpenter.
- [ ] **4.3 Azure AKS:** Control plane tiers, Azure CNI Overlay vs Pod Subnet, Microsoft Entra Workload ID, Application Gateway Ingress Controller (AGIC), Azure Disk/Files CSI, AKS Karpenter/VMSS.
- [ ] **4.4 Multi-Cloud Cross-Environment Drills:** Cloud API throttling, IAM/Entra/GCP Workload Identity permission denied, cross-AZ PVC attachment deadlock (`WaitForFirstConsumer`), LoadBalancer `Pending` external IP.

## Module 5: Production Observability & Monitoring
- [ ] **5.1 Observability Architecture:** Metrics, Logs, Traces; Push vs Pull; RED & USE methods.
- [ ] **5.2 Prometheus & Thanos:** Scraper, TSDB WAL, PromQL (`rate`, `irate`, `histogram_quantile`), `node-exporter`, `kube-state-metrics`, `cAdvisor`, Thanos HA.
- [ ] **5.3 Grafana & Alertmanager:** `kube-prometheus-stack`, Golden Signals dashboards, Alertmanager routing (Slack/PagerDuty), inhibition & alert fatigue prevention.
- [ ] **5.4 Centralized Logging & Tracing:** `Fluent Bit`, Grafana Loki (LogQL) vs EFK/OpenSearch, OpenTelemetry Collector + Grafana Tempo / Jaeger.
- [ ] **5.5 CI/CD & Cloud Monitoring:** Jenkins/GitLab Runner metrics, AWS CloudWatch/AMP, Azure Monitor, GCP Cloud Operations.
- [ ] **5.6 Observability Failure Drills:** Prometheus `OOMKilled` (high label cardinality), Fluent Bit backpressure log drops, missing `kube-state-metrics`, alert storms during node drain.
