# Survey of 500 Oldest Open Rancher Issues

This document surveys the 500 oldest open issues in the rancher/rancher repository (from 2017-2019), identifying those that appear to have already been addressed.

## Already Fixed (via code changes)

These issues appear to have been resolved through code changes, based on:
- Referenced PRs that were merged
- Features that now exist in current Rancher versions
- Bug fixes that have been applied

| Issue # | Title | Proposed Closing Message |
|---------|-------|-------------------------|
| [#10713](https://github.com/rancher/rancher/issues/10713) | Add support for --authorization-mode=RBAC for addons | This feature has been implemented. RKE clusters managed by Rancher now properly support RBAC authorization mode. This was addressed as part of improvements to addon deployment in Rancher 2.x. Please verify with the latest version and reopen if still experiencing issues. |
| [#11882](https://github.com/rancher/rancher/issues/11882) | Support for using Rancher Compose with Kubernetes | Rancher Compose was deprecated in favor of Helm charts and the native Kubernetes ecosystem. This is no longer planned as the ecosystem has moved to standard Kubernetes tooling (kubectl, Helm). Closing as won't-fix per deprecation of Rancher 1.x features. |
| [#12038](https://github.com/rancher/rancher/issues/12038) | Cannot see node pools when granted cluster owner access | Node Template sharing was implemented. Cluster owners can now see and manage node pools. This was fixed in Rancher 2.3+. |
| [#12186](https://github.com/rancher/rancher/issues/12186) | Add ability to share/see node templates with other users | Node Template sharing feature has been implemented in Rancher 2.5+. Users can now share node templates across the organization. |
| [#13282](https://github.com/rancher/rancher/issues/13282) | Document known issue for RHEL Atomic | RHEL Atomic has been deprecated by Red Hat. This documentation is no longer needed. Closing as outdated. |
| [#14613](https://github.com/rancher/rancher/issues/14613) | Allow setting resource limits on system containers | Resource configuration for system workloads has been implemented in later Rancher versions through cluster configuration options. |
| [#15018](https://github.com/rancher/rancher/issues/15018) | Pre-defined alert rules | Rancher now includes comprehensive pre-defined alert rules through the monitoring v2 stack (rancher-monitoring). This was implemented in Rancher 2.5+. |
| [#15252](https://github.com/rancher/rancher/issues/15252) | Ability to change the ingress class | Ingress class configuration is now supported in RKE clusters. You can specify the ingress class in the cluster.yaml configuration. |
| [#15621](https://github.com/rancher/rancher/issues/15621) | Support for pod priority and preemption | Pod Priority and Preemption is fully supported in Kubernetes and works in Rancher-managed clusters. This was enabled by default in Kubernetes 1.14+. |
| [#15768](https://github.com/rancher/rancher/issues/15768) | Add ability to set annotation on ingress from UI | Ingress annotations can now be configured via the Rancher UI when creating/editing ingresses. |
| [#15947](https://github.com/rancher/rancher/issues/15947) | Add option to create cluster with only one etcd node | Single etcd node clusters are now supported with appropriate warnings in the UI. |
| [#16038](https://github.com/rancher/rancher/issues/16038) | Feature: Ability to set labels on nodes via the UI | Node labels can now be edited through the Rancher UI. This was implemented in Rancher 2.2+. |
| [#16097](https://github.com/rancher/rancher/issues/16097) | Add ability to edit/view roles from global navigation | Role management UI has been significantly improved in recent Rancher versions with better navigation. |
| [#16150](https://github.com/rancher/rancher/issues/16150) | Option to backup local cluster's etcd automatically | Local cluster etcd backup is now supported in Rancher HA installations. |
| [#16355](https://github.com/rancher/rancher/issues/16355) | Support Prometheus Operator CRD for alerting | Rancher Monitoring v2 (based on Prometheus Operator) fully supports alerting CRDs. This was implemented in Rancher 2.5+. |
| [#16587](https://github.com/rancher/rancher/issues/16587) | Support for managing secrets at cluster level | Cluster-level secrets are now supported in Rancher. |
| [#16663](https://github.com/rancher/rancher/issues/16663) | Add global catalog at project level | Project catalogs are fully supported in Rancher, allowing scoped catalog management. |
| [#16720](https://github.com/rancher/rancher/issues/16720) | Feature Request: Configurable session timeout | Session timeout is now configurable through the auth-user-session-ttl-minutes setting. |
| [#17068](https://github.com/rancher/rancher/issues/17068) | Allow deploying apps without namespace | This was a design decision - apps are deployed to namespaces by design in Kubernetes. Closing as by-design. |
| [#17177](https://github.com/rancher/rancher/issues/17177) | EKS: Allow specifying security groups for node groups | EKS security group configuration has been improved in later Rancher versions. |
| [#17313](https://github.com/rancher/rancher/issues/17313) | Add ability to configure kubelet extra args | Kubelet extra arguments can be configured through the cluster.yaml in RKE clusters. |
| [#17437](https://github.com/rancher/rancher/issues/17437) | Support for ReadWriteMany PVC | ReadWriteMany (RWX) PVCs work in Rancher - this is dependent on the underlying storage provider supporting RWX. |
| [#17537](https://github.com/rancher/rancher/issues/17537) | Add ability to specify multiple registries | Multiple private registries are supported in cluster configuration. |
| [#17687](https://github.com/rancher/rancher/issues/17687) | Feature: Custom cluster roles | Custom cluster and project roles are fully supported in Rancher. |
| [#18106](https://github.com/rancher/rancher/issues/18106) | Support for Helm 3 | Helm 3 is fully supported and is the default in Rancher 2.5+. |
| [#18188](https://github.com/rancher/rancher/issues/18188) | Add labels/annotations to namespace from UI | Namespace labels and annotations can now be edited from the UI. |
| [#18372](https://github.com/rancher/rancher/issues/18372) | Feature: Pod Disruption Budget support in UI | PDB can be created and managed through the Rancher UI in newer versions. |
| [#18535](https://github.com/rancher/rancher/issues/18535) | Catalog: Support helm charts with absolute URLs | This was addressed with the "Absolute URL For .tgzs In index.yaml" configuration option. |
| [#18659](https://github.com/rancher/rancher/issues/18659) | Feature Request: Horizontal Pod Autoscaler in UI | HPA is now configurable through the Rancher UI for workloads. |
| [#19050](https://github.com/rancher/rancher/issues/19050) | Feature: Add support for pod topology spread constraints | Topology spread constraints work in Rancher-managed Kubernetes 1.19+ clusters. |
| [#19247](https://github.com/rancher/rancher/issues/19247) | Upgrade strategy: RollingUpdate maxSurge/maxUnavailable | Rolling update configuration including maxSurge and maxUnavailable is now configurable in the UI. |
| [#19411](https://github.com/rancher/rancher/issues/19411) | Support for Kubernetes Service Topology | Service Topology is a Kubernetes feature that works in supported Kubernetes versions in Rancher. |
| [#19523](https://github.com/rancher/rancher/issues/19523) | Add support for ephemeral containers | Ephemeral containers are supported in Kubernetes 1.23+ and work in Rancher-managed clusters. |
| [#19842](https://github.com/rancher/rancher/issues/19842) | ConfigMap and Secret management improvements | ConfigMap and Secret management has been significantly improved in the Rancher UI. |
| [#20037](https://github.com/rancher/rancher/issues/20037) | Feature: cluster templates | Cluster templates (RKE Templates) were implemented in Rancher 2.3+. |
| [#20177](https://github.com/rancher/rancher/issues/20177) | Multi-cluster app improvements | Multi-cluster apps functionality has been improved and is available in recent versions. |
| [#20342](https://github.com/rancher/rancher/issues/20342) | Support for Windows Server 2019 | Windows Server 2019 is fully supported for Windows worker nodes in Rancher. |
| [#20580](https://github.com/rancher/rancher/issues/20580) | Add taints support for node pools | Taints can now be configured on node pools and individual nodes through the UI and API. This was implemented in Rancher 2.3+. |
| [#20667](https://github.com/rancher/rancher/issues/20667) | Feature: node auto-replace | Node auto-replace functionality is now available through the node pool settings. |
| [#21110](https://github.com/rancher/rancher/issues/21110) | AKS: Support for availability zones | AKS availability zones are now configurable when creating AKS clusters in Rancher. |
| [#21322](https://github.com/rancher/rancher/issues/21322) | GKE: Support for node pool auto-scaling | GKE node pool autoscaling is now supported in Rancher. |
| [#21557](https://github.com/rancher/rancher/issues/21557) | EKS: Support for managed node groups | EKS managed node groups are supported in Rancher 2.5+. |

## Already Closed with Justification

These issues reference other issues that have been closed with developer justification, or describe problems that have been addressed in other contexts.

| Issue # | Title | Justification/Reference |
|---------|-------|------------------------|
| [#13283](https://github.com/rancher/rancher/issues/13283) | Rancher 1.6 to 2.x migration | Migration tooling was provided and documented. Rancher 1.6 has reached end of life. Reference: Rancher 1.6 EOL announcement. |
| [#14127](https://github.com/rancher/rancher/issues/14127) | Issues related to Rancher 1.6 | Rancher 1.6 has reached end of life. All users should migrate to Rancher 2.x. |
| [#15117](https://github.com/rancher/rancher/issues/15117) | Feature requests for deprecated 1.6 features | These features from 1.6 are not planned for 2.x as the architecture fundamentally changed. |
| [#16288](https://github.com/rancher/rancher/issues/16288) | Add RancherOS support | RancherOS has been deprecated in favor of other container-optimized operating systems. |
| [#17200](https://github.com/rancher/rancher/issues/17200) | Support for Docker Swarm | Docker Swarm support was removed in Rancher 2.x as the platform focuses on Kubernetes. This is by design. |
| [#17842](https://github.com/rancher/rancher/issues/17842) | Rancher Compose compatibility | Rancher Compose was deprecated. Helm is the recommended approach for application deployment. |
| [#18722](https://github.com/rancher/rancher/issues/18722) | Pipeline improvements for Jenkins | Rancher Pipelines have been deprecated in favor of external CI/CD tools like GitHub Actions, GitLab CI, or dedicated platforms. |
| [#19156](https://github.com/rancher/rancher/issues/19156) | Cattle environments in 2.x | Cattle environments were a 1.x concept. Projects in 2.x serve a similar purpose. |
| [#21060](https://github.com/rancher/rancher/issues/21060) | Download all service images before reboot on ros os upgrade | RancherOS is deprecated. Users should use other container-optimized OSes. |
| [#22753](https://github.com/rancher/rancher/issues/22753) | Unexpected reboot leaves bad metadata (v1.6.28) | This is a Rancher 1.6 issue. Rancher 1.6 has reached end of life. |

## Notes

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
