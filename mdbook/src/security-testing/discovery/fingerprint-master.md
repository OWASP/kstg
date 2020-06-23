# Fingerprinting Master Node

The Kubernetes `kube-apiserver` exposes a REST API interface for cluster administrators to manage the cluster. This API server has distinct fingerprint, available to an unauthenticated user using which it is possible to fingerprint an API server.

## Version Endpoint

| Threat Model Attribute | Value                  |
|:---------------------- |:---------------------- |
| Attacker Position      | External               |
| Threat                 | Information Disclosure |

The Kubernetes API server exposes a version endpoint to unauthenticated user using which it is possible to fingerprint the version of Kubernetes API server.

```bash
curl -sk https://$API_HOST:$API_PORT/version
```

Produces output (example)

```json
{
  "major": "1",
  "minor": "18",
  "gitVersion": "v1.18.2",
  "gitCommit": "52c56ce7a8272c798dbc29846288d7cd9fbae032",
  "gitTreeState": "clean",
  "buildDate": "2020-04-30T20:19:45Z",
  "goVersion": "go1.13.9",
  "compiler": "gc",
  "platform": "linux/amd64"
}
```

A security tester can infer that the target is running `kube-apiserver` version `v1.18.2` based on the above JSON response from the API server.
