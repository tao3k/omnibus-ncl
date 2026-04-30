---
kind: SKILL.md
type: skill
title: "Nsjail Sandbox"
category: "security"
tags:
  - nsjail
  - sandbox
  - linux
name: nsjail
description: Use when configuring Linux sandboxing with nsjail, generating security profiles, or configuring process isolation for skills.
author: xiuxian-artisan-workshop
date: 2026-04-26T09:30-07:00
metadata:
  retrieval:
    saliency_base: 5.5
    decay_rate: 0.05
  version: "1.0.0"
  source: "https://github.com/tao3k/xiuxian-artisan-workshop/tree/main/packages/ncl/sandbox/nsjail"
  routing_keywords:
    - "nsjail"
    - "sandbox"
    - "linux"
    - "namespace"
    - "container"
    - "isolation"
    - "process"
    - "security"
    - "chroot"
    - "cgroups"
---

# Nsjail Skill

Linux sandboxing and process isolation using nsjail.

## Commands

| Command | Description |
|---------|-------------|
| [`nsjail_config`](#nsjail_config) | Generate nsjail configuration |
| [`nsjail_profile`](#nsjail_profile) | Generate nsjail profile |
| [`nsjail_run`](#nsjail_run) | Run command in nsjail |

### nsjail_config

Generate an nsjail configuration.

### nsjail_profile

Generate an nsjail profile.

### nsjail_run

Run a command in nsjail.

## Usage Examples

```python
# Generate minimal nsjail config
@omni("nsjail.nsjail_config", {"skill_id": "data-processor", "mode": "local"})

# Generate standard profile
@omni("nsjail.nsjail_profile", {"profile_type": "standard", "skill_id": "web-scraper"})

# Run command in nsjail
@omni("nsjail.nsjail_run", {"cmd": ["python3", "script.py"], "mode": "local"})
```

## Concepts

| Topic | Description | Reference |
|-------|-------------|-----------|
| Profile Types | Sandbox profiles | [profiles.md](references/profiles.md) |
| Resource Limits | CPU/memory limits | [rlimits.md](references/rlimits.md) |
| Network Policies | Network isolation | [network.md](references/network.md) |

## Best Practices

- Start with minimal profile, escalate as needed
- Use network deny unless required
- Set appropriate timeouts
- Use cgroups for resource control

## Related Skills

| Topic | Description | Reference |
|-------|-------------|-----------|
| Seatbelt | macOS sandboxing | [seatbelt](../seatbelt/SKILL.md) |
| NCL Modules | Nickel module patterns | [nickel-modules.md](packages/ncl/nickel-modules.md) |
