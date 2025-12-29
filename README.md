# Ideation Agent: Report & Pivot

Final report generator and pivot advisor for the Ideation multi-agent pipeline. Compiles comprehensive evaluation reports and suggests pivot directions if the idea was eliminated.

## Overview

This agent is part of the [Ideation Orchestrator](https://github.com/Othentic-Ai/ideation-claude) multi-agent system for validating startup ideas.

## Capabilities

- **Report Compilation**: Aggregates all phase outputs into cohesive report
- **Executive Summary**: Creates high-level findings summary
- **Score Summary**: Consolidates all validation scores
- **Pivot Suggestions**: If eliminated, provides 3-5 pivot directions
- **Next Steps**: Actionable recommendations with timeframes

## Usage

This agent is invoked by the Ideation Orchestrator as a native sub-agent:

```
Task: report-pivot
Prompt: Generate report for "{problem}" with session_id={session_id}
```

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `MEM0_API_KEY` | Yes | For Mem0 cloud storage |

## Output

The agent produces a comprehensive markdown report including:
- Session information and status
- Executive summary
- Scores summary table
- Market analysis (TAM/SAM/SOM)
- Customer segments
- Competitive landscape
- Technical considerations
- MVP recommendations
- Team requirements
- Business model
- Key risks and mitigations
- Validation experiments
- Recommended next steps
- **If eliminated**: Pivot recommendations with viability scores

## Part of Ideation Pipeline

```
Phase 1: PROBLEM VALIDATION (Parallel)
├── market-researcher
└── customer-solution
    ↓
Phase 2: SOLUTION VALIDATION
└── feasibility-scorer
    ↓
Phase 3: REPORT
└── report-pivot ← This agent
```

## License

MIT
