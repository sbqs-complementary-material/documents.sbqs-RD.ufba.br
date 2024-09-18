# Introduction to the Concept of ADRs

**Architectural Decision Records (ADRs)** are essential documents for capturing and communicating significant architectural decisions in software projects, offering a clear structure to rationalize and record these choices. This practice supports documentation and transparency, facilitating the understanding and review of decisions over time.

## Structure and ADR Template

We use the **Nygard** format for our ADRs, which includes clear sections such as **Context**, **Decision**, and **Consequences**. This format helps clarify the reasons behind each decision and its implications. For more details and examples of ADR templates, access our resource directory.

### File Naming Rules

The file should be named according to the pattern:

`0002-[tag]-adr-name.md`

- **Numbering:** Numbering should always be done with 4 digits, and an ADR (even if it has been rejected) cannot have the same number as another.
- **Spacing:** Spacing should always be done using the "-" character as in the example.
- **Possible Tags:** `[XX]`, `[XXX]`, `[XXXX]`, `[XXXXX]`, `[XXXXXX]`
- **Extension:** The file extension should always be `.md`
- **Lowercase:** The entire name should be written in lowercase letters.
- **ADR Name:** Should include short noun phrases and the inclusion of specific tags. Examples: `"[XX] use mysql database"`, `"[XXX] adopt postgresql database"`

These naming rules exist to make the file compatible with ADR analysis and tracking tools.

## Process for Creating and Maintaining ADRs

An ADR must be created whenever a decision is made regarding a [significant architectural requirement](docs/arq-when_to_open_an_ADR.md). The creation of ADRs can be initiated by any team member, following two types of classification:

- **Internal ADRs:** An ADR can be internal; in this case, it should start with the tag of each group. For this decision to be approved, approval from the team leader (advisor) is required.
- **Global ADRs:** An ADR can be global; in this case, it should start with the tag `[XXXXXX]`. For this decision to be approved, the architecture team needs to approve the decision. They are responsible for contacting the advisors of the teams affected by the decision and mediating consensus on the open decision.

To create an ADR, it is necessary to:

1. Create a copy of the template and fill it with the necessary information.
2. Insert this filled document into the standard directory.

The lifecycle of this ADR is the responsibility of its creator, ensuring the document's update and correction. The complete procedure is in the document: [ADR Lifecycle](docs/arq-cycle_of_life_of_the_ADR.md).

## Additional Resources

Below are documents to assist with the creation and maintenance of ADRs:

- [When to Create an ADR](docs/arq-when_to_open_an_ADR.md)
- [Best Practices for ADRs](docs/arq-standards.md)
- [Anti-patterns](https://www.ozimmer.ch/practices/2023/04/03/ADRCreation.html)


