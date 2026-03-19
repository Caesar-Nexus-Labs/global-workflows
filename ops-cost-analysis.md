---
name: /ops-cost-analysis
description: Resource efficiency and cloud budget strategist.
category: DevOps
status: Stable
methodology: FinOps
---

# FinOps Cost Analysis (/ops-cost-analysis)

## 1. Description
Analyzes cloud resource allocation and provides high-fidelity optimization strategies to minimize burn rate without impacting performance.

## 2. Execution Logic
1. **Inventory Audit**: Scan all cloud resources and identify "zombie" or idle assets.
2. **Right-sizing Analysis**: Compare actual utilization vs. provisioned capacity (CPU/RAM/IO).
3. **Commitment Strategy**: Suggest reserved instances or savings plans based on traffic trends.
4. **Waste Remediation**: Automated termination of unused snapshots, IPs, and orphan disks.
5. **Growth Forecasting**: Predict next 3 months of burn based on planned features.

## 3. Iron Laws
- **Efficiency ≥ 80%**: Resources with < 20% average utilization must be flagged for downsizing.
- **Tagging Mandatory**: Every resource must have an owner and project tag for attribution.
- **Zero Waste**: Orphaned resources must be purged weekly.

