# Tailscale service for Kubernetes on Wodby

Connect Kubernetes applications through Tailscale with Wodby.

This repository defines the Wodby service manifests and operational
configuration for Tailscale.

- [Tailscale service on Wodby](https://wodby.com/services/tailscale)
- [Browse Wodby services](https://wodby.com/services)
- [Wodby service documentation](https://wodby.com/docs/2.0/services/)
- [Service manifest reference](https://wodby.com/docs/2.0/services/template/)

## Wodby stacks using this service

- [OpenClaw application stack](https://github.com/wodby/stack-openclaw)
- [Tailscale application stack](https://github.com/wodby/stack-tailscale)

## Service overview

| Property | Manifest configuration |
| --- | --- |
| Service name | `tailscale` |
| Type | Application service |
| Versions | `1.94` by default |
| Workloads | `main` (Statefulset, primary) |
| Containers | `tailscale` using `tailscale/tailscale` |
| Endpoints | None |
| Service links | Service to serve (`serve`), optional |
| Application build | Not buildable from application source |
| Helm | chart `oci://registry-1.docker.io/wodby/tailscale`; version `0.1.0` |
| Configuration and operations | 1 integration slots, 1 volumes |

## Use this service

Use this service through [OpenClaw application stack](https://github.com/wodby/stack-openclaw), [Tailscale application stack](https://github.com/wodby/stack-tailscale), or reference
`tailscale` from a custom Wodby stack.

A service is a reusable component and does not deploy by itself. The stack
defines its links, settings, versions, resources, and relationship to the rest
of the application.

## Maintain a custom version

1. Fork this repository.
2. Edit the service manifest and referenced files.
3. Import the repository as a [Git-backed service](https://wodby.com/docs/2.0/services/create/#create-a-git-backed-service).
4. Reference the service from a stack manifest.

Keep service, workload, container, endpoint, link, volume, config, and
derivative names stable unless dependent stacks and app-level overrides are
updated at the same time.

Validate the manifests with:

```bash
wodby service validate-manifest service.yml --org <org-id>
```

See the [service manifest reference](https://wodby.com/docs/2.0/services/template/) and the [managed services index](https://github.com/wodby/services).
