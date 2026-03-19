---
name: "forge:monitor"
description: "Configure observability stacks (Prometheus, Grafana, ELK) for reliability."
category: "c36_devops"
status: "verified"
methodology: "methodology"
---

# Monitoring Setup (/forge-monitor)

## 5-Stage Caesar Nexus Logic

### Phase 1: Instrumentation
- **Action**: Add metrics and logging to the application.

### Phase 2: Collection
- Configure Prometheus/ELK to scrape and store data.

### Phase 3: Visualization
- **Action**: Invoke `/market-dashboard` for health metrics.

### Phase 4: Alerting
- Define thresholds and notification channels (Slack/PagerDuty).

### Phase 5: Validation
- Perform a simulated failure to verify alert triggers.

