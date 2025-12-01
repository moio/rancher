# Rancher/Rancher Duplicate Issues Report

This document summarizes potential duplicate issues found in the rancher/rancher repository based on analysis of open issues with similar error patterns, symptoms, and root causes.

---

## Group 1: "install-uuid not found" Error in Cluster Agent

### Issues:
- **#31534** - [failed to call leader func: settings.management.cattle.io "install-uuid" not found](https://github.com/rancher/rancher/issues/31534)
- **#31834** - [[EKS] Private EKS cluster is not available in proxy airgapped Rancher](https://github.com/rancher/rancher/issues/31834)

### Error Pattern:
```
time="2021-02-28T10:12:49Z" level=error msg="failed to call leader func: settings.management.cattle.io \"install-uuid\" not found"
```

### Reasoning:
Both issues report the exact same error message `settings.management.cattle.io "install-uuid" not found` occurring in the cattle-cluster-agent logs. Issue #31534 focuses on the general error when importing clusters, while #31834 specifically addresses private EKS clusters in proxy/airgapped environments. The root cause appears to be connectivity or authentication issues between the cattle-cluster-agent and the Rancher management server preventing access to the settings.management.cattle.io API.

### Suggested Action:
**Keep #31534 as the main tracking issue** since it's more general and has more engagement (20 comments). Issue #31834 could be closed as a duplicate with the message:
> "Closing as duplicate of #31534. The 'install-uuid not found' error you're experiencing has the same root cause - the cattle-cluster-agent cannot properly authenticate/connect to the Rancher server to retrieve management settings. The airgapped/proxy configuration in your case exacerbates this connectivity issue. Please follow #31534 for updates."

---

## Group 2: Cluster Stuck "Waiting for API server" / "Waiting for API to be available"

### Issues:
- **#23266** - [Clusters imported stuck at "Waiting for API server", with k8s-mode=external or embedded](https://github.com/rancher/rancher/issues/23266)
- **#32410** - [gkev2- private endpoint cluster on Rancher behind a proxy, gets stuck on "Waiting for API" status](https://github.com/rancher/rancher/issues/32410)

### Error Pattern:
Clusters get stuck in "Waiting for API server" or "Waiting for API to be available" state after the cattle-cluster-agent is deployed and establishes a websocket connection.

### Reasoning:
Both issues describe clusters becoming permanently stuck in a "Waiting for API" state. Issue #23266 focuses on this happening when Rancher is run in k8s-mode=external or k8s-mode=embedded, while #32410 focuses on private endpoint GKE clusters behind a proxy. Both share the same symptom where the cluster agent connects but the API never becomes available to Rancher. The underlying cause appears to be related to how Rancher handles private/isolated network configurations.

### Suggested Action:
These issues should be **kept separate** but **cross-linked** as they may share a common underlying cause but manifest in different deployment scenarios (embedded mode vs proxy/private endpoint). Recommend adding a comment linking them together for visibility:
> "This issue may be related to #23266 / #32410 which also involves clusters stuck in 'Waiting for API' state in specific network configurations."

---

## Group 3: Cattle Cluster Agent DNS Resolution Issues

### Issues:
- **#16454** - [Rancher Cattle Cluster Agent Could not Resolve Host](https://github.com/rancher/rancher/issues/16454) (138 comments, 47 👍)
- **#16757** - [cattle-node-agent daemonset created with "ClusterFirst" dnsPolicy even though it is running hostNetwork: true](https://github.com/rancher/rancher/issues/16757)

### Error Pattern:
```
ERROR: https://example.rancher.com/ping is not accessible (Could not resolve host: example.rancher.com)
```

### Reasoning:
Both issues relate to DNS resolution problems in cattle agents. Issue #16454 is a widely-reported bug where the cattle-cluster-agent fails to resolve the Rancher server hostname. Issue #16757 identifies a potential root cause: the cattle-node-agent daemonset uses `dnsPolicy: ClusterFirst` despite running with `hostNetwork: true`, which should use `ClusterFirstWithHostNet` to properly resolve DNS within the cluster.

### Suggested Action:
Issue **#16757 provides the fix explanation** for many instances of #16454. Consider adding a prominent comment to #16454:
> "If you're experiencing DNS resolution issues with the cattle-cluster-agent, note that #16757 identifies that the agent uses the incorrect dnsPolicy. As a workaround, ensure your host machines can resolve the Rancher server hostname, or configure kube-dns to resolve it. The proper fix would be to change dnsPolicy to 'ClusterFirstWithHostNet' for agents using hostNetwork."

These should be **cross-linked** rather than closed as duplicates since #16454 is the symptom and #16757 is one explanation of the root cause.

---

## Group 4: Cluster Provisioning/Status Issues When Nodes Unreachable

### Issues:
- **#19916** - [Cluster Stuck in Updating State when Nodes are Missing During Deletion](https://github.com/rancher/rancher/issues/19916)

### Error Pattern:
```
Failed to delete controlplane node [X.X.X.X] from cluster: Get https://...:6443/api/v1/nodes?timeout=30s: net/http: request canceled (Client.Timeout exceeded while awaiting headers)
```

### Reasoning:
This issue describes clusters getting stuck in "Updating" state when nodes are removed from the infrastructure before being properly drained from the cluster. The cluster tries to communicate with nodes that no longer exist, causing continuous timeout errors.

### Suggested Action:
This appears to be a **unique issue** without clear duplicates found. Should remain open with its current tracking.

---

## Group 5: Provisioning Issues with k8s 1.16+ and RBAC

### Issues:
- **#23525** - [cluster with k8s v1.16.2 fails to deploy, stuck in Provisioning status](https://github.com/rancher/rancher/issues/23525)

### Error Pattern:
```
clusterroles.rbac.authorization.k8s.io "proxy-clusterrole-kubeapiserver" is forbidden: User "u-xxx" cannot get resource "clusterroles" in API group "rbac.authorization.k8s.io" at the cluster scope
```

### Reasoning:
This issue describes clusters with k8s 1.16.2 getting stuck in provisioning due to RBAC permission issues. The cattle-cluster-agent cannot deploy because the user lacks proper RBAC permissions at the cluster scope.

### Suggested Action:
This appears to be a **unique issue** specific to k8s 1.16+ API changes. The issue is labeled for Windows as well, suggesting it may be a regression in that specific context.

---

## Summary of Recommended Actions

| Issue Group | Recommended Action |
|:----------------------------|:---------------------------------------------------|
| Group 1 (install-uuid) | Close #31834 as duplicate of #31534 |
| Group 2 (Waiting for API) | Cross-link #23266 and #32410 |
| Group 3 (DNS Resolution) | Cross-link #16454 and #16757, add explanation comment |
| Group 4 (Nodes Unreachable) | No duplicates found |
| Group 5 (k8s 1.16+ RBAC) | No duplicates found |

---

## Additional Notes

Many issues in the rancher/rancher repository share similar symptoms but have different root causes depending on:
- Deployment type (single install vs HA)
- Kubernetes version
- Cloud provider (AWS/EKS, GCP/GKE, Azure/AKS, custom)
- Network configuration (public, private, proxy, airgapped)
- Operating system and container runtime

Care should be taken when closing issues as duplicates to ensure the underlying causes are truly the same and not just manifesting with similar symptoms.

---

## Methodology

This analysis was conducted by:
1. Searching open issues in rancher/rancher using GitHub's issue search API
2. Identifying common error patterns and keywords (e.g., "install-uuid", "Could not resolve host", "Waiting for API", "cattle-cluster-agent")
3. Manually reviewing issue descriptions, error logs, and user comments to identify root cause similarities
4. Cross-referencing issues that share the same error messages or symptom patterns

*Report generated: 2025-12-01*
