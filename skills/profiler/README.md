# profiler

Systematic performance profiling for Node.js, Python, and Go applications. Identifies CPU, memory, and I/O bottlenecks; generates flamegraphs; analyzes bundle sizes; optimizes database queries; detects memory leaks; and runs load tests with k6 and Artillery.

## What it does

- **CPU profiling** — flamegraphs via clinic.js (Node.js), py-spy (Python), pprof (Go)
- **Memory profiling** — heap snapshots, leak detection, GC pressure analysis
- **Bundle analysis** — webpack-bundle-analyzer, Next.js bundle analyzer
- **Database optimization** — EXPLAIN ANALYZE, slow query log, N+1 detection
- **Load testing** — k6 scripts, Artillery scenarios, ramp-up patterns
- **Before/after measurement** — establish baseline, profile, optimize, verify

## When to use

- App is slow and you don't know where the bottleneck is
- P99 latency exceeds SLA before a release
- Memory usage grows over time (suspected leak)
- Bundle size increased after adding dependencies
- Preparing for a traffic spike
- Database queries taking >100ms

## Quick Start

```bash
# Analyze a project for performance risk indicators
python3 scripts/performance_profiler.py /path/to/project

# JSON output for CI integration
python3 scripts/performance_profiler.py /path/to/project --json

# Custom large-file threshold
python3 scripts/performance_profiler.py /path/to/project --large-file-threshold-kb 256
```

## Files

```text
profiler/
  SKILL.md                          — agent instructions and optimization playbook
  README.md                         — this file
  scripts/
    performance_profiler.py         — static analysis script (stdlib only, no dependencies)
  references/
    profiling-recipes.md            — copy-paste profiling commands for Node.js, Python, Go
```

## Requirements

- Python 3.8+ (for `scripts/performance_profiler.py` — no external packages needed)
- Language-specific tools are installed on demand as needed (clinic, py-spy, k6, etc.)

## Example output

```text
Performance Profile Report
Root: /path/to/project
Large-file threshold: 512.0KB

Dependency Counts
- Node: 47
- Python: 0
- Go: 0

Bundle Indicators
- Build directories present: .next
- Bundle-like files: 312
- Estimated weighted bundle size: 4821.34 KB

Large Files
- .next/static/chunks/framework.js: 1.2MB
- .next/static/chunks/main.js: 890.4KB
```
