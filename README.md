# Product Roadmapping

## Project Artifacts: Kickstarter Launch Check (completed 2026-11-06)

The seven required artifacts of the [project handout](07-project-handout.md), built for the Week 9
Kickstarter Launch Check project, plus the Phase 7 walkthrough:

| File | Purpose |
|---|---|
| [strategy-brief.md](strategy-brief.md) | Direction, choices, exclusions, objectives, constraints; defines the evidence labels used everywhere |
| [evidence-map.md](evidence-map.md) | Sources S01 to S07, findings F01 to F12, opportunities O01 to O06 |
| [initiative-register.md](initiative-register.md) | Initiatives I01 to I06 with objective, evidence, gates, stop signals; candidate approaches kept separate |
| [roadmap.md](roadmap.md) | Now-Next-Later as confidence horizons, exclusions, commitment language, change log |
| [roadmap-decision-log.md](roadmap-decision-log.md) | Decisions D-01 to D-12 with options considered |
| [roadmap-review.md](roadmap-review.md) | Review R1: the data licence (observed) and a sponsor request (scenario) |
| [ai-collaboration-log.md](ai-collaboration-log.md) | What Claude proposed, corrected and rejected, and what still awaits owner review |
| [walkthrough.md](walkthrough.md) | The ten-minute sponsor walkthrough (Phase 7) |

This Markdown learning path connects product vision, user evidence, strategy,
prioritization, and roadmap communication. Participants build an outcome-based
roadmap that communicates direction and uncertainty without turning early ideas
into feature promises or invented delivery dates.

## Project at a Glance

The project connects vision and evidence to an outcome-based roadmap that
communicates direction, confidence, and change without inventing commitments.

```mermaid
%%{init: {"theme":"base","themeVariables":{"fontFamily":"Arial","primaryTextColor":"#172033","lineColor":"#64748B"},"flowchart":{"curve":"basis","nodeSpacing":36,"rankSpacing":52}}}%%
flowchart LR
    Goal[Create an evidence-backed<br/>product roadmap]
    subgraph Direction["<b>1. Establish Direction and Opportunities</b>"]
        direction TB
        Vision[Vision and strategy]
        Evidence[User and business evidence]
        Opportunities[Prioritized opportunity areas]
        Vision --> Opportunities
        Evidence --> Opportunities
    end
    subgraph Roadmap["<b>2. Build the Roadmap</b>"]
        direction TB
        Initiatives[Outcome-based initiatives]
        Now[Now<br/>Committed learning]
        Next[Next<br/>Likely direction]
        Later[Later<br/>Open options]
        Traceability[Objectives, evidence,<br/>dependencies and risks]
        Initiatives --> Now
        Initiatives --> Next
        Initiatives --> Later
        Now --> Traceability
        Next --> Traceability
        Later --> Traceability
    end
    subgraph Govern["<b>3. Communicate and Govern Change</b>"]
        direction TB
        Audiences[Audience-specific<br/>roadmap views]
        Triggers[Review triggers<br/>and decision records]
        Output[Defensible roadmap<br/>and presentation]
        Audiences --> Output
        Triggers --> Output
        Output -. New evidence .-> Triggers
    end
    Goal --> Direction --> Roadmap --> Govern
    classDef goal fill:#172033,color:#FFFFFF,stroke:#172033,stroke-width:2px;
    classDef input fill:#FFFFFF,color:#172033,stroke:#4677A8,stroke-width:1.5px;
    classDef work fill:#FFFFFF,color:#172033,stroke:#3B8A5A,stroke-width:1.5px;
    classDef output fill:#FFFFFF,color:#172033,stroke:#B77A1F,stroke-width:1.5px;
    class Goal goal;
    class Vision,Evidence,Opportunities input;
    class Initiatives,Now,Next,Later,Traceability work;
    class Audiences,Triggers,Output output;
    style Direction fill:#F5F9FD,stroke:#9BB8D2,stroke-width:1.5px;
    style Roadmap fill:#F4FAF6,stroke:#9DC8AD,stroke-width:1.5px;
    style Govern fill:#FFFAEF,stroke:#D7B66B,stroke-width:1.5px;
```

## Learning Objectives

By the end of this repository, you should be able to:

- Distinguish a vision, strategy, roadmap, release plan, and delivery backlog.
- Turn user research findings into evidence-backed opportunities.
- Define initiatives as strategic problem areas with measurable outcomes.
- Select a roadmap format that fits the decision, audience, and uncertainty.
- Build and justify a Now-Next-Later roadmap using confidence horizons.
- Connect initiatives to objectives, evidence, dependencies, risks, and learning.
- Communicate commitments without presenting uncertain work as guaranteed.
- Maintain a roadmap through explicit review triggers and decision records.
- Use Claude Code for structure, critique, and maintenance while retaining human
  ownership of evidence and decisions.

## Learning Path

The modules build on each other in order.

| File / Folder | Description |
|---|---|
| [**01 - Vision and Product Strategy**](01-vision-and-product-strategy.md) | Connect the desired future, strategic choices, objectives, and roadmap. |
| [**02 - From Evidence to Opportunities**](02-from-evidence-to-opportunities.md) | Synthesize research without turning observations directly into features. |
| [**03 - Roadmaps as Strategic Communication**](03-roadmaps-as-strategic-communication.md) | Define roadmap initiatives, audiences, and the boundary between direction and delivery. |
| [**04 - Roadmap Formats and Confidence**](04-roadmap-formats-and-confidence.md) | Compare outcome, theme, Now-Next-Later, timeline, and release roadmaps. |
| [**05 - Roadmap Governance and Communication**](05-roadmap-governance-and-communication.md) | Review, adapt, and communicate a roadmap without hiding uncertainty or change. |
| [**06 - Claude Code as Roadmap Partner**](06-claude-code-as-roadmap-partner.md) | Delegate file creation, consistency checks, scenario analysis, and updates with approval gates. |
| [**07 - Project Handout**](07-project-handout.md) | Create, challenge, and present an evidence-backed roadmap for an original context. |

### Additional Folders and Files

| File / Folder | Description |
|---|---|
| [**assets**](assets/) | Local, attributed illustrations from product-management and research sources. |
| [**templates**](templates/) | Starting structures for evidence, strategy, initiatives, roadmap decisions, and reviews. |

## Getting Started

No Python environment is required for this repository.

1. Create a repository from this template and add collaborators when working
   in a group.
2. Clone the repository and open it locally.
3. Read the lesson files in numerical order.
4. Use Claude Code through any available interface and make the project files
   available to it when the handout introduces the working process.
5. Use the handout and templates to create the project artifacts.

## AI Collaboration Guidelines

Claude may structure supplied research, trace initiatives to objectives,
identify contradictions, and maintain approved files. It must not invent user
evidence, business targets, technical feasibility, stakeholder agreement, or
delivery commitments. Do not enter sensitive data, and record material AI
contributions that the group accepted, corrected, or rejected.

## References & Further Reading

- [GOV.UK Service Manual: Developing a Roadmap](https://www.gov.uk/service-manual/agile-delivery/developing-a-roadmap)
- [Roman Pichler: The Product Vision Board](https://www.romanpichler.com/tools/product-vision-board/)
- [ProdPad: Now-Next-Later Roadmap](https://www.prodpad.com/glossary/now-next-later-roadmap/)
- [Atlassian: Agile Roadmaps](https://www.atlassian.com/agile/product-management/roadmaps)
- [Interaction Design Foundation: Affinity Diagrams](https://www.interaction-design.org/literature/topics/affinity-diagram)
