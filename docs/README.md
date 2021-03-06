# Table of workloads

| Workload/tooling                                   | Short Description                         | Minimum Requirements                  |
|:-------------------------------------------------- |:----------------------------------------- | ------------------------------------- |
| [Tooling](tooling.md)                              | Setup pbench metric tools                 | Cluster-admin, Privileged Containers  |
| [Test](test.md)                                    | Test/Run your workload from ssh Container | Cluster-admin, Privileged Containers  |
| [Baseline](baseline.md)                            | Baseline metrics capture                  | Tooling job*                          |
| [Scale](scale.md)                                  | Scales worker nodes                       | Cluster-admin                         |
| [NodeVertical](nodevertical.md)                    | Node Kubelet Density                      | Labeling Nodes                        |
| [PodVertical](podvertical.md)                      | Max Pod Density                           | None                                  |
| [MasterVertical](mastervertical.md)                | Master Node Stress workload               | None                                  |
| [HTTP](http.md)                                    | HTTP ingress TPS/Latency                  | None                                  |
| [Network](network.md)                              | TCP/UDP Throughput/Latency                | Labeling Nodes, [See below](#network) |
| [Deployments Per Namespace](deployments-per-ns.md) | Maximum Deployments                       | None                                  |
| [PVCscale](pvscale.md)                             | PVCScale test                             | Working storageclass                  |

* Baseline job without a tooled cluster just idles a cluster.  The goal is to capture resource consumption over a period of time to characterize resource requirements thus tooling is required. (For now)

## Network

| Test                       | Requirement                                 |
|:-------------------------- |:------------------------------------------- |
| Pod 2 Pod                  | Labeling Nodes                              |
| Pod 2 Pod with HostNetwork | Labeling Nodes, Open firewall ports at Host |
| Service 2 Service          | Labeling Nodes                              |

## CI Pass/Fail

Each workload will implement a form of pass/fail criteria in order to flag if the tests have failed in CI.

| Workload/tooling                                   | Pass/Fail                     |
|:-------------------------------------------------- |:----------------------------- |
| [Tooling](tooling.md)                              | NA                            |
| [Test](test.md)                                    | NA                            |
| [Baseline](baseline.md)                            | NA                            |
| [Scale](scale.md)                                  | Yes: Test Duration            |
| [NodeVertical](nodevertical.md)                    | Yes: Exit Code, Test Duration |
| [PodVertical](podvertical.md)                      | In Progress                   |
| [MasterVertical](mastervertical.md)                | In Progress                   |
| [HTTP](http.md)                                    | No                            |
| [Network](network.md)                              | No                            |
| [Deployments Per Namespace](deployments-per-ns.md) | No                            |
| [PVCscale](pvscale.md)                             | No                            |
