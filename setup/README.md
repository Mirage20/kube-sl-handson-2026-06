# Setup (organizers)

Provisioning notes for whoever runs the platform for this hands-on. Attendees don't need this —
they start from a namespace that's already prepared and sign in with the credentials shown at the
event.

## Per-namespace provisioning

Each attendee works in their own namespace. A fresh namespace needs a Project, three Environments
(development / staging / production, all on the shared `ClusterDataPlane/default`), and a
DeploymentPipeline before the lab works. ClusterComponentTypes and ClusterResourceTypes are
cluster-scoped and already present, so they aren't recreated here.

Apply `namespace.yaml` from the repo root, swapping the namespace name per attendee (the manifest
uses `kube-sl-handson` as the example):

```bash
kubectl --context k3d-openchoreo apply -f setup/namespace.yaml
```

The namespace shows up in the portal's Create wizard within a few seconds.

## Notes

- **Observability:** if the observability plane isn't enabled, a component's LOGS / METRICS tabs
  show "not enabled" — enable it, or skip those tabs in the session.
- **Endpoint URLs** are per-environment and gateway-assigned; take them from the DEPLOY panel
  rather than hardcoding.
- **Deploy time** is roughly 30–60s per environment (image pull + pod start).

## Cleanup

```bash
kubectl --context k3d-openchoreo delete -f setup/namespace.yaml
```

Deleting the namespace cascades through the components, workloads, releases, and bindings.
