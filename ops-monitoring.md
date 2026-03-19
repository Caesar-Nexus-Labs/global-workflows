---
name: /ops-monitoring
description: Telemetry, logging, and visualization architect.
category: DevOps
status: Stable
methodology: Caesar Nexus Logic
---

# Observability Engine (/ops-monitoring)

## 1. Description
Provides real-time visibility into the system health through unified telemetry, logging, and performance metrics.

## 2. Caesar Nexus Execution Loop

### Phase 1: Instrumentation
- Automatic injection of OpenTelemetry hooks into the codebase.
- Configuration of Prometheus scraping targets for new services.

### Phase 2: Log Aggregation
- Centralization of logs using Loki/ELK stack with structured S-YAML formats.
- Setup of distributed tracing for high-load backend paths.

### Phase 3: Visualization
- Auto-generation of Grafana dashboards based on service profiles.
- Mapping of the "Golden Signals" (Latency, Traffic, Errors, Saturation).

### Phase 4: Alerting Logic
- Defining dynamic alert thresholds based on historical baseline drift.
- Integration with `/ops-incident` for automated paging.

### Phase 5: Audit
- Continuous review of metric drift and recording of state in the Technical Journal.

## 3. Iron Laws
- **Golden Signals Mandatory**: Only dashboards tracking the 4 Golden Signals are considered production-ready.
- **Trace Everything**: All high-latency operations (>200ms) must have associated traces.
- **Data Privacy**: Logs must be scrubbed of PII and secrets before ingestion.

