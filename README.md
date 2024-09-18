# Developer Guide

This repository provides a comprehensive list of documents to guide developers in writing clear and 
well-organized Python code. Here you will find standards for commit messages, coding styles, dependency management, 
and code commenting guidelines.


List of documents:

- **[Coding Style](docs/coding_style.md)** - Aims to guide the use with best practices to write a Python code within PEP8 (Python Enhancement Proposal 8) compliance.
- **[Comment Patterns](docs/template_code.md)** - Aims to guide the use on how to comment the code accordingly `pdoc` standard to auto-generates API documentation.
- **[Commits Standard](docs/commits.md)** - Aims to guide the use of the tool to standardize and management commits in a `Git` project.
- **[Dependencies Managements](docs/dependencies.md)** - Aims to guide the use of the dependency management package with Poetry.
- **[Branches Managements](docs/branching_model.md)** - Aims to guide the use of branches management with Trunk-Based approach.

# Architectural management and docuemntation instructions

Here we provide the documents with the processes, guides and instructions to manage the system architecture

List of documents:

- **[Introduction to ADRs](docs/arq-introduction.md)** - Provides an introduction to Architectural Decision Records (ADRs), explaining their purpose and structure, including naming conventions and templates used for maintaining clarity and consistency in documenting decisions.
- **[Best Practices for ADRs](docs/arq-standards.md)** - Discusses best practices for maintaining and managing ADRs, promoting ownership, preserving ADR history, and addressing non-conforming code.
- **[Deployment Documentation Template](docs/arq-deployment_documentation_creation_instructions.md)** - Provides instructions and a standardized template for creating deployment documentation for Python modules, focusing on dependencies, environment variables, and Docker container builds.
- **[ADR Lifecycle](docs/arq-cycle_of_life_of_the_ADR.md)** - Describes the lifecycle of an ADR, including creation, ownership, review processes, and states (Proposed, Accepted, Superseded). It outlines how ADRs should be maintained as immutable after acceptance.
- **[When to Create an ADR](docs/arq-when_to_open_an_ADR.md)* - Explains when to create an ADR by identifying architecturally significant requirements and other criteria that demand ADR documentation.
