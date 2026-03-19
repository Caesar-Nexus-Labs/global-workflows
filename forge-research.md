# /forge-research

> **Deep-Dive Technical Scouting** — Benchmarking, library evaluation, and architecture research.

## Metadata

- **Slug**: /forge-research
- **Type**: Research & Investigation
- **Agents**: Researcher, Technical Lead, Architect
- **Calls**: /forge-scout (for detailed codebase analysis)

## Description

Conducts in-depth technical research including:
- Library/framework evaluation & benchmarking
- Architecture pattern research
- Performance profiling & optimization opportunities
- Competitive technology analysis
- Industry best practices review
- RFCs and proposal evaluation
- Technology feasibility studies

## Parameters

| Flag | Type | Description |
|------|------|-------------|
| --topic | string | Library, pattern, architecture, performance, etc |
| --depth | string | shallow, medium, deep |
| --include-benchmarks | boolean | Run comparative benchmarks |
| --references | array | Specific libraries/frameworks to evaluate |

## Output

```json
{
  "research_id": "research-auth-libs-20260317",
  "topic": "Authentication Libraries",
  "candidates": 8,
  "top_recommendation": "passport-js",
  "trade_offs": {
    "option_a": "Pros: flexible, Cons: complex setup",
    "option_b": "Pros: simple, Cons: limited features"
  },
  "benchmark_results": {
    "latency_ms": 2.5,
    "throughput_rps": 40000
  }
}
```

## Related

- Calls: /forge-scout
- Used by: /forge-design, /forge-bootstrap, /forge-refactor

**Status**: PROD-READY ✅
**Version**: 1.0.0
