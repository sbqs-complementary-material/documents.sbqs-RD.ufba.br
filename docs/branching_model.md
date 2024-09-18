# Branching Model User Guide for Python Project Development

## Introduction

This guide provides a structured approach to managing branches in a Python development project using trunk-based 
development, emphasizing short-lived branches, pull requests, merge squash, rebase, and no fast-forward merges. 
This model ensures a streamlined workflow, promoting code quality, collaboration, and efficient integration.

### Trunk-Based Development

**Trunk-based development** is a version control strategy where developers merge small, frequent updates to a single main 
branch, known as the 'trunk' or 'main'. This minimizes integration issues and ensures continuous integration and delivery.

### Branching Strategy

1. **Main Branch**
   - The `main` branch represents the production-ready state of the project.
   - All feature branches are merged into `main` via pull requests.

2. **Feature Branches**
   - Use short-lived feature branches for developing new features, bug fixes, or experiments.
   - Branches should be named descriptively (e.g., `feature/add-login`, `bugfix/fix-login-error`).

### Workflow

1. **Creating a Feature Branch**
   - Always branch off from the `main` branch.
   ```sh
   git checkout main
   git pull origin main
   git checkout -b feature/your-feature-name
   ```

2. **Developing on a Feature Branch**
   - Commit changes frequently with meaningful messages.
   ```sh
   git add .
   git commit -m "feat: add detailed commit message describing the change"
   ```

3. **Rebasing with Main**
   - Regularly rebase your feature branch with the `main` branch to keep it up-to-date.
   - Check the following website to know more about [Git Rebase](https://www.atlassian.com/br/git/tutorials/rewriting-history/git-rebase)
   ```sh
   git checkout main
   git pull origin main
   git checkout feature/your-feature-name
   git rebase main
   ```

4. **Creating a Pull Request**
   - Once the feature is complete, push the branch to the remote repository.
   ```sh
   git push origin feature/your-feature-name
   ```
   - Open a pull request (PR) against the `main` branch.
   - Ensure your PR includes a clear description of the changes and references any relevant issues or tasks.

5. **Reviewing a Pull Request**
   - Team members review the PR for code quality, functionality, and adherence to project standards.
   - Address feedback by making changes and pushing them to the same feature branch.

6. **Merging a Pull Request**
   - Once approved, squash and merge the PR to maintain a clean commit history.
   ```sh
   git checkout main
   git pull origin main
   git checkout feature/your-feature-name
   git rebase main
   git checkout main
   git merge --squash feature/your-feature-name
   git commit -m "Merge feature/your-feature-name: Description of the feature"
   git push origin main
   ```
   - Delete the feature branch after merging.
   ```sh
   git branch -d feature/your-feature-name
   git push origin --delete feature/your-feature-name
   ```

### Additional Guidelines

- **No Fast-Forward Merges (no-ff)**
  - Always use `--no-ff` to ensure that all merges create a merge commit. This helps maintain a clear project history.
  ```sh
  git merge --no-ff feature/your-feature-name
  ```

- **Merge Squash**
  - Squash commits to combine all changes from a feature branch into a single commit. This keeps the `main` branch history concise and easy to understand.
  ```sh
  git merge --squash feature/your-feature-name
  ```

- **Commit Messages**
  - Use descriptive commit messages that explain the why behind the changes.
  - Follow the format: `type(scope): description` (e.g., `feat(login): add user authentication`).

- **Code Reviews**
  - Ensure all PRs undergo a thorough review process.
  - Use tools like linters and automated tests to catch issues early.

## Conclusion

Following this branching model ensures a clean, manageable, and efficient workflow for Python project development. 
By adhering to trunk-based development, using short-lived branches, and maintaining a disciplined approach to merging 
and rebasing, teams can deliver high-quality software consistently and rapidly.

### To become more familiar with the trunk-based specifications, check out the following link [Trunk Based Development](https://trunkbaseddevelopment.com/)