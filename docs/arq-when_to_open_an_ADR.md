# When to Create an ADR

An ADR should be created whenever a decision is made regarding a significant architectural requirement. To assist in identifying such requirements, the following characteristics have been outlined to help determine which requirements are of significant interest:

## Characteristics of Architecturally Significant Requirements

- **Wide Impact:** Requirements that affect multiple parts of the system are generally significant. This includes changes that impact components, other requirements, code modules, or stakeholders. If a requirement influences various aspects of the system, it is likely to have architectural significance.

- **Trade-Off Points:** Requirements that involve trade-offs, where multiple needs cannot be equally met, are crucial because they require strategic architectural choices. Such requirements may force architects to prioritize certain aspects over others, influencing key design decisions.

- **Constraints and Non-Negotiable Requirements:** Requirements that limit design options and cannot be negotiated are significant, as they dictate specific architectural decisions. These constraints can be technical or non-technical (e.g., financial, time constraints) and often limit the available design alternatives.

- **Breaking Assumptions:** Requirements that challenge fundamental architectural assumptions require significant changes and are therefore important. When a new requirement contradicts existing assumptions, it may necessitate a reevaluation of the current architecture.

- **Difficult to Achieve:** Technically challenging or difficult-to-implement requirements may be architecturally significant due to the complexity involved in fulfilling them. These requirements often require innovative solutions or significant architectural modifications.

- **Quality Attributes:** Requirements that specify quality attributes such as performance, security, or usability are generally significant because they define critical aspects of user experience and system operation. Quality attributes often influence architectural decisions to ensure that the system meets these essential criteria.

- **Core Functionality:** Requirements related to the system's core functionalities tend to be significant, as they capture the essence of the expected software behavior and the primary expectations of users. These requirements are central to the system's purpose and often dictate key architectural elements.

- **Constraints:** Requirements imposing constraints, whether technical or non-technical (such as financial limitations or time constraints), are considered significant because they limit architectural design options. Constraints can influence decisions on technology stacks, frameworks, or architectural patterns used.

- **Application Environment:** Requirements that define the environment in which the system will operate (such as specific hardware, operating systems, or corporate networks) are significant, influencing the necessary architecture for the software to function properly under these conditions.

Whenever a decision needs to be made regarding a requirement that exhibits any of the characteristics described above, the creation of an ADR is necessary.

For more details on how to characterize architecturally significant requirements, you can refer to the article: [Characterizing Architecturally Significant Requirements](https://ieeexplore.ieee.org/document/6365165). The indicators mentioned have been derived and paraphrased based on concepts from this article.


