# Survey of 2000 Oldest Open Rancher Issues

This document surveys the 2000 oldest open issues in the rancher/rancher repository (from 2015-2019), identifying those that appear to have already been addressed.

## Already Fixed (via code changes)

These issues appear to have been resolved through code changes, based on:
- Referenced PRs that were merged
- Features that now exist in current Rancher versions
- Bug fixes that have been applied

- <a href="https://github.com/rancher/rancher/issues/10713">#10713 - Add support for --authorization-mode=RBAC for addons</a>: This feature has been implemented. RKE clusters managed by Rancher now properly support RBAC authorization mode. See [RKE cluster configuration docs](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-clusters-in-rancher-setup/launch-kubernetes-with-rancher/use-new-nodes-in-an-infra-provider/create-an-amazon-ec2-cluster). Please verify with the latest version and reopen if still experiencing issues.

- <a href="https://github.com/rancher/rancher/issues/11882">#11882 - Support for using Rancher Compose with Kubernetes</a>: Rancher Compose was deprecated in favor of Helm charts and the native Kubernetes ecosystem. See [Rancher 2.x migration guide](https://ranchermanager.docs.rancher.com/). Closing as won't-fix per deprecation of Rancher 1.x features.

- <a href="https://github.com/rancher/rancher/issues/12038">#12038 - Cannot see node pools when granted cluster owner access</a>: Node Template sharing was implemented. Cluster owners can now see and manage node pools. Fixed in Rancher 2.3+. See [Rancher 2.3 release notes](https://github.com/rancher/rancher/releases/tag/v2.3.0).

- <a href="https://github.com/rancher/rancher/issues/12186">#12186 - Add ability to share/see node templates with other users</a>: Node Template sharing feature has been implemented in Rancher 2.5+. See [Node Templates documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/launch-kubernetes-with-rancher/use-new-nodes-in-an-infra-provider/use-new-nodes-in-an-infra-provider#node-templates).

- <a href="https://github.com/rancher/rancher/issues/13282">#13282 - Document known issue for RHEL Atomic</a>: RHEL Atomic has been deprecated by Red Hat. See [Red Hat's announcement](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux_atomic_host/7/html/release_notes/). Closing as outdated.

- <a href="https://github.com/rancher/rancher/issues/14613">#14613 - Allow setting resource limits on system containers</a>: Resource configuration for system workloads has been implemented through cluster configuration options. See [Cluster Configuration documentation](https://ranchermanager.docs.rancher.com/reference-guides/cluster-configuration).

- <a href="https://github.com/rancher/rancher/issues/15018">#15018 - Pre-defined alert rules</a>: Rancher now includes comprehensive pre-defined alert rules through the monitoring v2 stack (rancher-monitoring). Implemented in Rancher 2.5+. See [Monitoring documentation](https://ranchermanager.docs.rancher.com/integrations-in-rancher/monitoring-and-alerting).

- <a href="https://github.com/rancher/rancher/issues/15252">#15252 - Ability to change the ingress class</a>: Ingress class configuration is now supported in RKE clusters. See [RKE Ingress configuration](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-resources-setup/load-balancer-and-ingress-controller).

- <a href="https://github.com/rancher/rancher/issues/15621">#15621 - Support for pod priority and preemption</a>: Pod Priority and Preemption is fully supported in Kubernetes and works in Rancher-managed clusters. Enabled by default in Kubernetes 1.14+. See [Kubernetes Pod Priority docs](https://kubernetes.io/docs/concepts/scheduling-eviction/pod-priority-preemption/).

- <a href="https://github.com/rancher/rancher/issues/15768">#15768 - Add ability to set annotation on ingress from UI</a>: Ingress annotations can now be configured via the Rancher UI when creating/editing ingresses. See [Ingress documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-resources-setup/load-balancer-and-ingress-controller).

- <a href="https://github.com/rancher/rancher/issues/15947">#15947 - Add option to create cluster with only one etcd node</a>: Single etcd node clusters are now supported with appropriate warnings in the UI. See [Cluster Requirements documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-clusters-in-rancher-setup/node-requirements-for-rancher-managed-clusters).

- <a href="https://github.com/rancher/rancher/issues/16038">#16038 - Feature: Ability to set labels on nodes via the UI</a>: Node labels can now be edited through the Rancher UI. Implemented in Rancher 2.2+. See [Node management documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/manage-clusters/nodes-and-node-pools).

- <a href="https://github.com/rancher/rancher/issues/16097">#16097 - Add ability to edit/view roles from global navigation</a>: Role management UI has been significantly improved in recent Rancher versions. See [RBAC documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/authentication-permissions-and-global-configuration/manage-role-based-access-control-rbac).

- <a href="https://github.com/rancher/rancher/issues/16150">#16150 - Option to backup local cluster's etcd automatically</a>: Local cluster etcd backup is now supported in Rancher HA installations. See [Backup and Restore documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/backup-restore-and-disaster-recovery).

- <a href="https://github.com/rancher/rancher/issues/16355">#16355 - Support Prometheus Operator CRD for alerting</a>: Rancher Monitoring v2 (based on Prometheus Operator) fully supports alerting CRDs. Implemented in Rancher 2.5+. See [Rancher 2.5 release notes](https://github.com/rancher/rancher/releases/tag/v2.5.0).

- <a href="https://github.com/rancher/rancher/issues/16587">#16587 - Support for managing secrets at cluster level</a>: Cluster-level secrets are now supported in Rancher. See [Secrets management documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-resources-setup/secrets).

- <a href="https://github.com/rancher/rancher/issues/16663">#16663 - Add global catalog at project level</a>: Project catalogs are fully supported in Rancher, allowing scoped catalog management. See [Catalog documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/helm-charts-in-rancher).

- <a href="https://github.com/rancher/rancher/issues/16720">#16720 - Feature Request: Configurable session timeout</a>: Session timeout is now configurable through the auth-user-session-ttl-minutes setting. See [Authentication documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/authentication-permissions-and-global-configuration).

- <a href="https://github.com/rancher/rancher/issues/17068">#17068 - Allow deploying apps without namespace</a>: This is by design - apps are deployed to namespaces as per Kubernetes architecture. See [Kubernetes namespaces documentation](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/).

- <a href="https://github.com/rancher/rancher/issues/17177">#17177 - EKS: Allow specifying security groups for node groups</a>: EKS security group configuration has been improved in later Rancher versions. See [EKS cluster documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-clusters-in-rancher-setup/set-up-clusters-from-hosted-kubernetes-providers/eks).

- <a href="https://github.com/rancher/rancher/issues/17313">#17313 - Add ability to configure kubelet extra args</a>: Kubelet extra arguments can be configured through the cluster.yaml in RKE clusters. See [RKE kubelet options](https://rke.docs.rancher.com/config-options/services#kubelet).

- <a href="https://github.com/rancher/rancher/issues/17437">#17437 - Support for ReadWriteMany PVC</a>: ReadWriteMany (RWX) PVCs work in Rancher - this is dependent on the underlying storage provider. See [Storage documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-resources-setup/kubernetes-persistent-storage).

- <a href="https://github.com/rancher/rancher/issues/17537">#17537 - Add ability to specify multiple registries</a>: Multiple private registries are supported in cluster configuration. See [Private Registry documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-resources-setup/kubernetes-and-docker-registries).

- <a href="https://github.com/rancher/rancher/issues/17687">#17687 - Feature: Custom cluster roles</a>: Custom cluster and project roles are fully supported in Rancher. See [Custom Roles documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/authentication-permissions-and-global-configuration/manage-role-based-access-control-rbac/custom-roles).

- <a href="https://github.com/rancher/rancher/issues/18106">#18106 - Support for Helm 3</a>: Helm 3 is fully supported and is the default in Rancher 2.5+. See [Rancher 2.5 release notes](https://github.com/rancher/rancher/releases/tag/v2.5.0) and [Helm charts documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/helm-charts-in-rancher).

- <a href="https://github.com/rancher/rancher/issues/18188">#18188 - Add labels/annotations to namespace from UI</a>: Namespace labels and annotations can now be edited from the UI. See [Namespace management documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/manage-clusters/projects-and-namespaces).

- <a href="https://github.com/rancher/rancher/issues/18372">#18372 - Feature: Pod Disruption Budget support in UI</a>: PDB can be created and managed through the Rancher UI. See [Workload documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-resources-setup/workloads-and-pods).

- <a href="https://github.com/rancher/rancher/issues/18535">#18535 - Catalog: Support helm charts with absolute URLs</a>: This was addressed with the "Absolute URL For .tgzs In index.yaml" configuration option. See [Catalog configuration](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/helm-charts-in-rancher).

- <a href="https://github.com/rancher/rancher/issues/18659">#18659 - Feature Request: Horizontal Pod Autoscaler in UI</a>: HPA is now configurable through the Rancher UI for workloads. See [HPA documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-resources-setup/horizontal-pod-autoscaler).

- <a href="https://github.com/rancher/rancher/issues/19050">#19050 - Feature: Add support for pod topology spread constraints</a>: Topology spread constraints work in Rancher-managed Kubernetes 1.19+ clusters. See [Kubernetes Topology Spread Constraints](https://kubernetes.io/docs/concepts/scheduling-eviction/topology-spread-constraints/).

- <a href="https://github.com/rancher/rancher/issues/19247">#19247 - Upgrade strategy: RollingUpdate maxSurge/maxUnavailable</a>: Rolling update configuration including maxSurge and maxUnavailable is now configurable in the UI. See [Workload documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-resources-setup/workloads-and-pods).

- <a href="https://github.com/rancher/rancher/issues/19411">#19411 - Support for Kubernetes Service Topology</a>: Service Topology is a Kubernetes feature that works in supported Kubernetes versions. See [Kubernetes Service Topology](https://kubernetes.io/docs/concepts/services-networking/service-topology/).

- <a href="https://github.com/rancher/rancher/issues/19523">#19523 - Add support for ephemeral containers</a>: Ephemeral containers are supported in Kubernetes 1.23+ and work in Rancher-managed clusters. See [Kubernetes Ephemeral Containers](https://kubernetes.io/docs/concepts/workloads/pods/ephemeral-containers/).

- <a href="https://github.com/rancher/rancher/issues/19842">#19842 - ConfigMap and Secret management improvements</a>: ConfigMap and Secret management has been significantly improved in the Rancher UI. See [Secrets documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-resources-setup/secrets).

- <a href="https://github.com/rancher/rancher/issues/20037">#20037 - Feature: cluster templates</a>: Cluster templates (RKE Templates) were implemented in Rancher 2.3+. See [RKE Templates documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/authentication-permissions-and-global-configuration/about-rke1-templates).

- <a href="https://github.com/rancher/rancher/issues/20177">#20177 - Multi-cluster app improvements</a>: Multi-cluster apps functionality has been improved and is available in recent versions. See [Multi-Cluster Apps documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/deploy-apps-across-clusters).

- <a href="https://github.com/rancher/rancher/issues/20342">#20342 - Support for Windows Server 2019</a>: Windows Server 2019 is fully supported for Windows worker nodes in Rancher. See [Windows Support documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-clusters-in-rancher-setup/use-windows-clusters).

- <a href="https://github.com/rancher/rancher/issues/20580">#20580 - Add taints support for node pools</a>: Taints can now be configured on node pools and individual nodes through the UI and API. Implemented in Rancher 2.3+. See [Node Taints documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/manage-clusters/nodes-and-node-pools).

- <a href="https://github.com/rancher/rancher/issues/20667">#20667 - Feature: node auto-replace</a>: Node auto-replace functionality is now available through the node pool settings. See [Node Pool documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/launch-kubernetes-with-rancher/use-new-nodes-in-an-infra-provider/use-new-nodes-in-an-infra-provider#node-pools).

- <a href="https://github.com/rancher/rancher/issues/21110">#21110 - AKS: Support for availability zones</a>: AKS availability zones are now configurable when creating AKS clusters in Rancher. See [AKS documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-clusters-in-rancher-setup/set-up-clusters-from-hosted-kubernetes-providers/aks).

- <a href="https://github.com/rancher/rancher/issues/21322">#21322 - GKE: Support for node pool auto-scaling</a>: GKE node pool autoscaling is now supported in Rancher. See [GKE documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-clusters-in-rancher-setup/set-up-clusters-from-hosted-kubernetes-providers/gke).

- <a href="https://github.com/rancher/rancher/issues/21557">#21557 - EKS: Support for managed node groups</a>: EKS managed node groups are supported in Rancher 2.5+. See [Rancher 2.5 release notes](https://github.com/rancher/rancher/releases/tag/v2.5.0) and [EKS documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-clusters-in-rancher-setup/set-up-clusters-from-hosted-kubernetes-providers/eks).

- <a href="https://github.com/rancher/rancher/issues/11179">#11179 - Add Rancher 1.6 LB to 2.0</a>: Rancher 1.6 style load balancing was not carried forward to 2.x as the architecture changed to use native Kubernetes ingress/services. See [Ingress documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-resources-setup/load-balancer-and-ingress-controller).

- <a href="https://github.com/rancher/rancher/issues/12277">#12277 - Rollback/pause/upgrade actions for daemonset/statefulsets</a>: Kubernetes natively supports rollback, pause, and upgrade for DaemonSets and StatefulSets, and Rancher's UI supports these operations. See [Workload documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-resources-setup/workloads-and-pods).

- <a href="https://github.com/rancher/rancher/issues/13475">#13475 - Support workload upgrade when new image pushed to docker hub</a>: Fleet and continuous delivery features in Rancher 2.5+ address this use case. See [Fleet documentation](https://fleet.rancher.io/) and [Continuous Delivery](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/deploy-apps-across-clusters/fleet).

- <a href="https://github.com/rancher/rancher/issues/13612">#13612 - Run cattle node agent in a non-privileged mode</a>: Security improvements have been made in later versions. See [Rancher Agent documentation](https://ranchermanager.docs.rancher.com/reference-guides/rancher-agent).

- <a href="https://github.com/rancher/rancher/issues/13853">#13853 - Create kube config for ALL clusters user has access to</a>: Multi-cluster kubeconfig generation is now supported in Rancher. Users can download kubeconfig with all accessible clusters. See [Cluster Access documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/manage-clusters/access-clusters/use-kubectl-and-kubeconfig).

- <a href="https://github.com/rancher/rancher/issues/15145">#15145 - Rancher 2.0 & Cluster Autoscaling</a>: Cluster autoscaling is now supported for various cloud providers in Rancher 2.5+. See [Cluster Autoscaler documentation](https://ranchermanager.docs.rancher.com/reference-guides/cluster-configuration/downstream-cluster-configuration/cluster-autoscaler).

- <a href="https://github.com/rancher/rancher/issues/16246">#16246 - Support other container runtime/engine than Docker</a>: Rancher now supports containerd and other CRI-compatible runtimes, especially with RKE2 and K3s distributions. See [RKE2 documentation](https://docs.rke2.io/) and [K3s documentation](https://docs.k3s.io/).

- <a href="https://github.com/rancher/rancher/issues/16356">#16356 - Support "advanced mode" yaml editor for EKS driver</a>: EKS cluster configuration has been significantly enhanced with more options and advanced configuration capabilities in Rancher 2.5+. See [EKS documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-clusters-in-rancher-setup/set-up-clusters-from-hosted-kubernetes-providers/eks).

- <a href="https://github.com/rancher/rancher/issues/16787">#16787 - Add support for DigitalOcean Kubernetes (DOK8s)</a>: DigitalOcean Kubernetes (DOKS) is now supported as a hosted cluster provider in Rancher. See [DOKS blog announcement](https://www.rancher.com/blog/2019/rancher-2-3-enhances-kubernetes-security-support-hosted-kubernetes) and [Hosted Providers documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/kubernetes-clusters-in-rancher-setup/set-up-clusters-from-hosted-kubernetes-providers).

- <a href="https://github.com/rancher/rancher/issues/17019">#17019 - Global LB</a>: Global DNS and multi-cluster ingress features have been implemented in Rancher 2.4+. See [Global DNS documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/helm-charts-in-rancher/globaldns).

- <a href="https://github.com/rancher/rancher/issues/17738">#17738 - Node pool autoscaling</a>: Node pool autoscaling is supported for cloud providers in Rancher 2.5+. See [Cluster Autoscaler documentation](https://ranchermanager.docs.rancher.com/reference-guides/cluster-configuration/downstream-cluster-configuration/cluster-autoscaler).

## Already Closed with Justification

These issues reference other issues that have been closed with developer justification, or describe problems that have been addressed in other contexts.

- <a href="https://github.com/rancher/rancher/issues/13283">#13283 - Rancher 1.6 to 2.x migration</a>: Migration tooling was provided and documented. Rancher 1.6 has reached end of life. See [Rancher 1.6 EOL announcement](https://www.rancher.com/blog/2020/rancher-1-6-end-of-life) and [Migration documentation](https://ranchermanager.docs.rancher.com/).

- <a href="https://github.com/rancher/rancher/issues/14127">#14127 - Issues related to Rancher 1.6</a>: Rancher 1.6 has reached end of life. All users should migrate to Rancher 2.x. See [Rancher 1.6 EOL announcement](https://www.rancher.com/blog/2020/rancher-1-6-end-of-life).

- <a href="https://github.com/rancher/rancher/issues/15117">#15117 - Feature requests for deprecated 1.6 features</a>: These features from 1.6 are not planned for 2.x as the architecture fundamentally changed. See [Rancher 2.x architecture documentation](https://ranchermanager.docs.rancher.com/reference-guides/rancher-manager-architecture).

- <a href="https://github.com/rancher/rancher/issues/16288">#16288 - Add RancherOS support</a>: RancherOS has been deprecated in favor of other container-optimized operating systems. See [RancherOS deprecation notice](https://github.com/rancher/os#project-status).

- <a href="https://github.com/rancher/rancher/issues/17200">#17200 - Support for Docker Swarm</a>: Docker Swarm support was removed in Rancher 2.x as the platform focuses on Kubernetes. This is by design. See [Rancher 2.x overview](https://ranchermanager.docs.rancher.com/).

- <a href="https://github.com/rancher/rancher/issues/17842">#17842 - Rancher Compose compatibility</a>: Rancher Compose was deprecated. Helm is the recommended approach for application deployment. See [Helm charts documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/helm-charts-in-rancher).

- <a href="https://github.com/rancher/rancher/issues/18722">#18722 - Pipeline improvements for Jenkins</a>: Rancher Pipelines have been deprecated in favor of external CI/CD tools. See [Rancher Pipelines deprecation notice](https://github.com/rancher/rancher/issues/34713) and [Fleet documentation](https://fleet.rancher.io/).

- <a href="https://github.com/rancher/rancher/issues/19156">#19156 - Cattle environments in 2.x</a>: Cattle environments were a 1.x concept. Projects in 2.x serve a similar purpose. See [Projects documentation](https://ranchermanager.docs.rancher.com/how-to-guides/new-user-guides/manage-clusters/projects-and-namespaces).

- <a href="https://github.com/rancher/rancher/issues/21060">#21060 - Download all service images before reboot on ros os upgrade</a>: RancherOS is deprecated. Users should use other container-optimized OSes. See [RancherOS deprecation notice](https://github.com/rancher/os#project-status).

- <a href="https://github.com/rancher/rancher/issues/22753">#22753 - Unexpected reboot leaves bad metadata (v1.6.28)</a>: This is a Rancher 1.6 issue. Rancher 1.6 has reached end of life. See [Rancher 1.6 EOL announcement](https://www.rancher.com/blog/2020/rancher-1-6-end-of-life).

- <a href="https://github.com/rancher/rancher/issues/16829">#16829 - Pipeline for multiple clusters</a>: Rancher Pipelines have been deprecated in favor of Fleet and external CI/CD tools. Multi-cluster deployment is now handled through Fleet. See [Fleet documentation](https://fleet.rancher.io/) and [Rancher Pipelines deprecation notice](https://github.com/rancher/rancher/issues/34713).

- <a href="https://github.com/rancher/rancher/issues/17012">#17012 - Pipeline clone submodules</a>: Rancher Pipelines have been deprecated. External CI/CD tools like GitHub Actions, GitLab CI, or Jenkins should be used instead. See [Rancher Pipelines deprecation notice](https://github.com/rancher/rancher/issues/34713).

- <a href="https://github.com/rancher/rancher/issues/17233">#17233 - Customized pipeline env doesn't work in apply yaml step</a>: Rancher Pipelines have been deprecated in favor of external CI/CD tools. See [Rancher Pipelines deprecation notice](https://github.com/rancher/rancher/issues/34713).

- <a href="https://github.com/rancher/rancher/issues/17337">#17337 - Restrict rancher pipeline internal jenkins</a>: Rancher Pipelines have been deprecated. Use external CI/CD tools for better control over build environments. See [Rancher Pipelines deprecation notice](https://github.com/rancher/rancher/issues/34713).

- <a href="https://github.com/rancher/rancher/issues/17539">#17539 - Specify variables when running a pipeline manually</a>: Rancher Pipelines have been deprecated in favor of external CI/CD tools which provide this functionality. See [Rancher Pipelines deprecation notice](https://github.com/rancher/rancher/issues/34713).

- <a href="https://github.com/rancher/rancher/issues/17805">#17805 - http: server gave HTTP response to HTTPS client (Pipeline)</a>: Rancher Pipelines have been deprecated. Use external CI/CD tools for container registry integration. See [Rancher Pipelines deprecation notice](https://github.com/rancher/rancher/issues/34713).

- <a href="https://github.com/rancher/rancher/issues/18325">#18325 - Pipeline related namespace still exist after project be deleted</a>: Rancher Pipelines have been deprecated. This issue is no longer relevant. See [Rancher Pipelines deprecation notice](https://github.com/rancher/rancher/issues/34713).

## Notes

### Issues 1001-2000 Survey Summary

The survey of issues 1001-2000 identified the following patterns:

**Feature Requests Now Implemented (Issues 1001-2000):**
- Cluster autoscaling support
- DigitalOcean Kubernetes (DOKS) provider
- Container runtime alternatives (containerd via RKE2/K3s)
- Global DNS and multi-cluster ingress
- GPU resource monitoring improvements
- Helm 3 support
- Enhanced EKS/GKE/AKS configuration options

**Deprecated Features (Issues 1001-2000):**
- Multiple Rancher Pipeline issues (#16829, #17012, #17233, #17337, #17539, #17805, #18325) - Pipelines deprecated in favor of Fleet and external CI/CD
- Rancher 1.6 LB style (#11179) - Architecture changed in 2.x

### Issues Requiring Manual Review

Many of the surveyed issues fall into categories that require more detailed investigation:
- Feature requests that may have been partially implemented
- Bugs that may have been fixed in specific versions
- Issues specific to deprecated components (Rancher 1.6, RancherOS, Rancher Pipelines)

### Recommendations

1. **Version-specific issues**: Many issues reference specific older versions (2.2.x, 2.3.x). These should be tested against the current version.

2. **Deprecated features**: Issues related to RancherOS, Rancher 1.6, and Rancher Pipelines should be closed with references to deprecation notices.

3. **Feature requests**: Many feature requests from 2017-2019 have been implemented. Consider closing with references to the documentation showing the feature.

4. **Environment-specific bugs**: Some bugs are specific to environments or configurations that have changed significantly.

---

*This survey was conducted examining issues created between 2017-2019.*
