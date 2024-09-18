# Best Practices in ADRs

## Promote Ownership
Every project team member should be empowered to create and own an ADR. This practice distributes the architectural research work among team members and relieves the solutions architect or team lead. It also fosters a sense of ownership in the decision-making process, which helps the team adopt these decisions more quickly instead of treating them as decisions imposed by higher levels of the organization.

## Preserve the ADR History
ADRs should have a change history, and each change should have an owner. When the owner of the ADR updates it, they should:
- Change the status of the old ADR to **Superseded**.
- Note their changes in the change history of the new ADR.
- Keep the old ADR in the decision record.

## Schedule Regular Review Meetings
If you are on a new (greenfield) project, the ADR process can be quite intense at the beginning. We recommend establishing a cadence of regular ADR discussion and review meetings before or after the daily stand-up. With this approach, the defined ADRs will stabilize in two or three sprints, and you can build a solid foundation with fewer meetings.

## Address Non-Compliant Code
The ADR process does not resolve the issue of non-compliant legacy code. If you have legacy code that does not support the established ADRs, you can:
- Gradually update the outdated codebase or artifacts while introducing new changes.
- Your team can decide to explicitly refactor the code by creating technical debt tasks.

*Text translated from the following source: [Best practices](https://docs.aws.amazon.com/prescriptive-guidance/latest/architectural-decision-records/best-practices.html)*
