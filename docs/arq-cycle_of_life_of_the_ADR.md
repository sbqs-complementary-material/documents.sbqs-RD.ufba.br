# ADR Lifecycle

An **Architectural Decision Record (ADR)** is a document that describes a significant choice about the software architecture that the team plans to build. Each ADR outlines the architectural decision, its context, and its consequences. ADRs have states and, therefore, follow a lifecycle.

## Scope of the ADR Process

Project members should create an ADR for each architecturally significant decision that affects the software project or product, including:

- **Structure** (e.g., patterns like microservices)
- **Non-functional requirements** (security, high availability, and fault tolerance)
- **Dependencies** (component coupling)
- **Interfaces** (APIs and published contracts)
- **Construction techniques** (libraries, frameworks, tools, and processes)

Functional and non-functional requirements are the most common inputs for the ADR process.

## Content of the ADR

When the team identifies the need for an ADR, a team member begins writing the ADR based on a project template. The template simplifies the creation of the ADR and ensures that the ADR captures all relevant information. At a minimum, each ADR should define the context of the decision, the decision itself, and the consequences of the decision for the project and its deliverables.

## ADR Adoption Process

Any team member can create an ADR, but the team must establish a definition of ownership for an ADR. Each author who is the owner of an ADR must actively maintain and communicate the content of the ADR. Other team members can always contribute to an ADR. If the content of an ADR changes before the team accepts it, the owner must approve these changes.

### ADR Review Process

1. The ADR owner provides the ADR in the **Proposed** state at the beginning of the process.
2. The ADR owner then initiates the ADR review process.
3. The project team, including the owner, reviews the ADR. The review meeting should begin with dedicated time to read the ADR.
4. During the review phase, the ADR owner reads and discusses each comment with the team.
5. If the team identifies action points to improve the ADR, the ADR's state remains **Proposed**.
6. The team may also decide to reject the ADR. In this case, the ADR owner adds a reason for the rejection.
7. If the team approves the ADR, the owner adds a timestamp, version, and list of stakeholders. The owner then updates the state to **Accepted**.

The ADRs and the decision log they create represent decisions made by the team and provide a history of all decisions. The team uses the ADRs as a reference during code and architecture reviews whenever possible.

### ADR Revision Process

ADRs should be treated as immutable documents after the team accepts or rejects them. Changes to an existing ADR require creating a new ADR, establishing a review process for the new ADR, and approving it. If the team approves the new ADR, the owner must change the state of the old ADR to **Superseded**.
