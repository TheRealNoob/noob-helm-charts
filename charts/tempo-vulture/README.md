# tempo-vulture Helm Chart

Grafana Tempo Vulture - A tool to monitor Tempo performance.

Sources

* <https://github.com/grafana/tempo>

## Installing the Chart

### OCI Registry

OCI registries are preferred in Helm as they implement unified storage, distribution, and improved security.
It does lack some features like the native ability to search chart versions.
For production however, OCI is recommended.

To install from an OCI registry:

```console
helm install RELEASE-NAME oci://ghcr.io/grafana-community/helm-charts/tempo-vulture
```

### Helm Repository

To install from a non-OCI registry:

```console
helm repo add grafana-community https://grafana-community.github.io/helm-charts
helm repo update
helm install RELEASE-NAME grafana-community/tempo-vulture
```

## Uninstalling the Chart

To removes all of the Kubernetes objects associated with the Helm chart release:

```console
helm uninstall RELEASE-NAME
```

## Configuration

Vulture only works with Jaeger gRPC, so make sure 14250 is open on your distributor. You don't need to specify the port in the distributor URL.

Example configuration:
```yaml
tempoAddress:
    push: http://tempo-tempo-distributed-distributor
    query: http://tempo-tempo-distributed-query-frontend:3100
```
