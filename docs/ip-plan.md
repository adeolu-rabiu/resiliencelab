
# ResilienceLab — IP Addressing Plan

## 1. Purpose

Define the planned IP networks for a synthetic,
two-Trust hybrid infrastructure environment.

## 2. Existing Networks

The Proxmox host already has management and
internal lab networking.

Existing management IP addresses and sensitive
host configuration are not published here.

Network bridge configurations must be verified
before implementing new VLANs or VRFs.

## 3. Proposed Trust North Networks

| Zone | Planned subnet |
|---|---|
| Clinical | 10.10.10.0/24 |
| Corporate | 10.20.10.0/24 |
| Medical Devices | 10.30.10.0/24 |
| Guest | 10.40.10.0/24 |
| Management | 10.50.10.0/24 |
| Services | 10.60.10.0/24 |

## 4. Proposed Trust South Networks

| Zone | Planned subnet |
|---|---|
| Clinical | 10.110.10.0/24 |
| Corporate | 10.120.10.0/24 |
| Medical Devices | 10.130.10.0/24 |
| Guest | 10.140.10.0/24 |
| Management | 10.150.10.0/24 |
| Services | 10.160.10.0/24 |

## 5. Cloud Addressing

Proposed cloud address reservation:

10.200.0.0/16

Cloud subnets will be defined during Phase 5.

## 6. Security Principles

- Separate clinical, corporate and guest traffic.
- Restrict inter-zone traffic using firewall policy.
- Prevent unintended routing between Trusts.
- Reserve management access for authorised users.
- Do not route synthetic networks into the home LAN.
- Test for address conflicts before deployment.

## 7. Validation

Pending:

- Check subnet overlap with existing networks.
- Confirm bridge and VLAN design.
- Verify routing boundaries.
- Document approved traffic flows.
