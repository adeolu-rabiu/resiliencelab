
# ResilienceLab — Proxmox Resource Plan

## 1. Project Environment

Project: ResilienceLab 2.0

Hypervisor: Proxmox VE 9.2.3

Host: rabtech

Development VM: 5000 (resilience-dev)

Purpose: Build and validate a synthetic two-Trust
hybrid infrastructure resilience environment.

## 2. Host Resources

| Resource | Capacity |
|---|---|
| Logical CPU threads | 4 |
| Physical RAM | Approximately 62 GiB |
| vmdata | Approximately 916 GiB total |
| datastore2tb | Approximately 1.79 TiB total |
| datastore256 | Approximately 234 GiB total |

Resource figures must be verified against the
latest Proxmox baseline before major deployment.

## 3. Existing Workloads

| VM ID | Name | Current role |
|---|---|---|
| 100 | eve-ng-01 | Network emulation |
| 101 | cp-1 | Kubernetes control plane |
| 102 | worker-1 | Kubernetes worker |
| 103 | worker-2 | Kubernetes worker |
| 104 | prism-ncu-observability | Monitoring workload |
| 110 | cloudworkspace | Existing workspace |
| 500 | DO-NOT-STOP-obot-ubuntu | Existing O-BOT service |
| 5000 | resilience-dev | ResilienceLab development |

VM 500 is an existing running service and must not
be stopped by ResilienceLab deployment scripts.

## 4. Development VM Allocation

VM ID: 5000

Operating system: Ubuntu Server

CPU: 2 vCPU (planned allocation)

RAM: 4 GiB (planned allocation)

Disk: 100 GiB (planned allocation)

Bridge: vmbr0 (verify actual configuration)

Storage: vmdata (verify actual configuration)

## 5. Resource Management Policy

- Keep at least 25% host RAM available where feasible.
- Avoid running all laboratory workloads together.
- Monitor CPU contention and memory pressure.
- Keep existing production-like services separate.
- Use backups before risky configuration changes.
- Prefer sequential testing of resource-heavy workloads.

## 6. Engineering Decisions

The lab is CPU-constrained relative to memory
capacity, so workloads will be started selectively.

Trust North will be hosted in Proxmox.

Trust South will initially be simulated.

Cloud workloads will be provisioned only when
the relevant project phase requires them.

## 7. Validation

Pending:

- Confirm current VM 5000 specification.
- Confirm storage placement.
- Record CPU and memory utilisation.
- Check network bridge allocations.
- Capture Proxmox baseline evidence.
