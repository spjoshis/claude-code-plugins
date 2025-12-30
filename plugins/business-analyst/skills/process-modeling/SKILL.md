---
name: process-modeling
description: Master process modeling with BPMN, flowcharts, swimlane diagrams, and process optimization techniques for business process improvement.
---

# Process Modeling

Create clear process models using BPMN, flowcharts, and swimlane diagrams to analyze, document, and optimize business processes.

## When to Use This Skill

- Documenting current processes (AS-IS)
- Designing future processes (TO-BE)
- Analyzing process inefficiencies
- Communicating workflows
- Identifying automation opportunities
- Standardizing procedures
- Training and onboarding
- Process improvement initiatives

## Core Concepts

### 1. BPMN (Business Process Model and Notation)

**Key Elements:**
- **Events**: Start, intermediate, end
- **Activities**: Tasks, sub-processes
- **Gateways**: Decisions, parallel, exclusive
- **Sequence Flows**: Process flow
- **Pools/Lanes**: Participants, roles

**Example BPMN:**
```
[Start] → [Receive Order] → <Payment OK?> → [Process Order] → [Ship] → [End]
                                     ↓
                                [Cancel Order] → [Notify Customer] → [End]
```

### 2. Swimlane Diagrams

**Structure:**
```
Customer    | [Browse] → [Select] → [Checkout] → [Receive]
System      |            [Validate] → [Process] → [Send Email]
Warehouse   |                         [Pick] → [Pack] → [Ship]
```

### 3. Flowchart Symbols

- Rectangle: Process/Activity
- Diamond: Decision
- Oval: Start/End
- Arrow: Flow direction
- Parallelogram: Input/Output

## Best Practices

1. **Start simple** - High-level first, then detail
2. **Use standard notation** - BPMN or UML
3. **Show exceptions** - Error paths and edge cases
4. **Validate with users** - Ensure accuracy
5. **Keep readable** - Clear labels, logical flow
6. **Document assumptions** - Note constraints
7. **Version control** - Track changes
8. **Focus on value** - Highlight improvements

## Resources

- **BPMN 2.0 Specification**: OMG standard
- **Lucidchart**: Process modeling tool
- **Draw.io**: Free diagramming tool
