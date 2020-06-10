# Threat Actors

| Actor                   | Description                                                                                                                                             |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| External Attacker       | An attacker who is external to the cluster and is unauthenticated                                                                                       |
| Internal Attacker       | An attacker who has some access in the cluster, such as an attacker with container access (Attacker in a Pod)                                           |
| Malicious Internal User | A user, such as administrator or developer, who uses their privileged position maliciously against the system, or stolen credentials used for the same. |
| Administrator           | An actual administrator of the system, tasked with operating and maintaining the cluster as a whole                                                     |
| Developer               | An application developer, who is deploying application to a cluster, either directly or through another user such as administrator                      |
| End User                | An external user of an application hosted by a cluster                                                                                                  |

We will primarily focus on two type of threat actors in *Kubernetes Security Testing Guide (KSTG)*, however we will refer to other threat actors as required.

1. External Attacker
2. Internal Attacker (Attacker in a Pod)

## Reference

* https://github.com/kubernetes/community/blob/master/wg-security-audit/
