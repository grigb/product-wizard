# Deep Research Prompt Generator

**Category**: Research, Analysis  
**Tags**: `#research` `#analysis` `#prompt-generation` `#deep-research`  
**Use Case**: Generating comprehensive research prompts for complex technical, market, or academic investigations  
**Complexity**: Large (> 500 words)  
**Created**: 2025-10-01  
**Last Updated**: 2025-10-01

## Overview

This prompt is designed to generate deep research prompts that can be executed by AI agents to produce comprehensive, evidence-based research reports. It creates structured research assignments with clear methodology, scope, and output specifications.

## When to Use

Use this prompt when you need to:
- Generate comprehensive research prompts for complex topics
- Create structured research assignments for AI agents
- Ensure thorough, evidence-based research with clear deliverables
- Research technical domains, market analysis, or academic literature
- Produce research reports that inform stakeholders with technical, financial, or policy implications

## Prerequisites

- A clear research topic or domain to investigate
- Understanding of the research context and stakeholder needs
- Access to research tools and databases for the executing agent

## The Prompt

```
## INSTRUCTION TO AGENT

Your task is to **generate a deep research prompt**, not to answer any question.
The `<INPUT_CONTEXT>` is raw material (omitted here, replaced with placeholder). Use it only to build the research prompt.
Do not solve or answer the content directly.



<INPUT_CONTEXT>

[ YOUR RESEARCH TOPIC HERE ]

</INPUT_CONTEXT>




<DEEP_RESEARCH_PROMPT_TASK version="2025-09-30">

### RESEARCHER ROLE

You are an expert in the relevant research domain with 15+ years of applied and academic experience. You combine theoretical grounding with practical engineering knowledge. You write with precision, rigor, and an evidence‑driven style. Your role is to design a deep research assignment that can be executed by another agent without needing further clarification.

### EXECUTION DIRECTIVE

ASSIGNMENT ID: RES-2025-[AXIS]-001
Research Type: [market analysis | technical evaluation | academic literature survey | policy review]
Research Method: peer‑reviewed papers, preprints, benchmarks, vendor docs, analyst reports, case studies
Decision Context: The deliverable must inform stakeholders with clear technical, financial, or policy implications.
Deliverable Form: Single inline markdown report. If length exceeds runtime limits, follow Segmented Delivery Protocol (Segment 1..N) while maintaining depth.

Objectivity: Include pros and cons, risks, trade‑offs, and confidence levels. Distinguish fact from speculation. Report gaps explicitly.

### SCOPE SPECIFICATION

* Define at least 8–12 objects of study on the canonical axis (tools, methods, platforms, policies, etc.).
* Provide 200+ words of analysis per object.
* Executive summary ≥500 words.
* Timeframe: Emphasize most recent 12–24 months, with historical grounding if needed.
* Geography: Global unless otherwise specified.
* Inclusion: Open‑source and proprietary equally.
* Exclusion: Defunct products unless historically relevant.
* Adjacent categories may be included if they illuminate gaps.
* Minimum relevance threshold: ≥30%.
* Explicitly list all inclusions and exclusions.

### CONTEXT SATURATION

Provide a fictionalized but detailed deployment context: team composition, budget, timeline, previous failures, measurable success criteria, and stakeholder needs. Ensure ≥500 words of environment description so the downstream research agent understands stakes and constraints.

### RESEARCH METHODOLOGY

* Specify exact search strategies and sample queries.
* Define evaluation framework and comparison dimensions.
* Evidence rules: prioritize peer‑reviewed or vendor‑authored docs; flag blog‑only claims as low confidence.
* Language policy: output in English; summarize non‑English with translation confidence.
* Ordering: rank by likelihood of meeting requirements and evidence strength.
* Discovery: expand seed list through adjacent categories, OSS repositories, conference agendas, and analyst quadrants.

### OUTPUT SPECIFICATIONS

* Format: unstructured markdown. No JSON, CSV, or file attachments.
* Structure:

  * # [Main Research Title]
  * ## Executive Summary [≥500 words]
  * ## Domain Overview (include Inventory Preview)
  * ## Detailed Findings (≥200 words per object)
  * ## Comparative Analysis
  * ## Implementation Considerations
  * ## Recommendations
  * ## Conclusion and Next Steps
* Depth: ≥3,500 words total; target ≥4,000.
* Segmented Delivery Protocol: Segment 1 = title, executive summary, domain overview; Segments 2..N = detailed findings; Final Segment = analysis, recommendations, conclusion.
* Quality standards: professional tone, technical accuracy, balanced perspective, evidence‑based.
* Output enforcement: deliver inline only, no links or attachments, no XML/JSON wrappers.

</DEEP_RESEARCH_PROMPT_TASK>

## ENFORCEMENT

Output must be one or more complete deep research prompts following this template.
Do not provide answers or analysis.
```

## Usage Examples

### Example 1: Technical Evaluation Research
**Input**: "AI/ML model deployment platforms for enterprise use"

**Expected Output**: A comprehensive research prompt that generates a detailed analysis of 8-12 AI/ML deployment platforms, including technical specifications, pricing, use cases, and implementation considerations.

### Example 2: Market Analysis Research
**Input**: "Open source database solutions for high-throughput applications"

**Expected Output**: A research prompt that creates a thorough market analysis of open source databases, comparing performance, scalability, community support, and enterprise adoption.

## Variations

### Variation 1: Academic Literature Survey
Modify the research type to focus on peer-reviewed papers and academic sources for theoretical or foundational research.

### Variation 2: Policy Review
Adjust the scope to focus on regulatory frameworks, compliance requirements, and policy implications.

### Variation 3: Competitive Analysis
Narrow the focus to direct competitors and market positioning analysis.

## Tips & Best Practices

- Replace `[ YOUR RESEARCH TOPIC HERE ]` with a specific, well-defined research question
- Ensure the research topic is specific enough to generate meaningful comparisons
- Consider the target audience and their decision-making needs
- Use the context saturation section to provide realistic constraints and scenarios
- Specify clear success criteria and measurable outcomes

## Common Pitfalls

- **Too broad topics**: Avoid overly general research areas that lack focus
- **Missing context**: Ensure the deployment context is detailed and realistic
- **Unclear objectives**: Make sure the research type and methodology align with stakeholder needs
- **Insufficient scope**: Ensure 8-12 objects of study are specified for comprehensive analysis

## Related Prompts

- [Conceptual Gap-Filling](./small-prompts.md#conceptual-gap-filling) - For identifying missing elements in system discussions
- [Analysis & Research category](./index.md#analysis--research) - Other research-focused prompts

## Notes

This prompt is particularly effective for generating research assignments that require:
- Comprehensive coverage of a domain
- Evidence-based analysis with confidence levels
- Clear stakeholder communication
- Structured deliverables with specific word counts and formatting requirements

The generated research prompts can be used by AI agents to produce professional-grade research reports suitable for technical decision-making, market analysis, or academic investigation.

---

*This prompt is part of the Product Wizard Prompt Library. See [index.md](./index.md) for the complete catalog.*
