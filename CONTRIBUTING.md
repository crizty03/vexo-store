# Contributing Guidelines

## Branching Strategy

We follow a strict Git flow. Direct pushes to `main` or `develop` are **forbidden**. All changes must come through Pull Requests.

- **main**: Production-ready code. Protected branch.
    - *Source*: Merges from `release/*` or `hotfix/*` only.
    - *Tagging*: All commits on main must be tagged (e.g., `v1.0.0`).
- **develop**: Integration branch.
    - *Source*: Merges from `feature/*`.
- **feature/name**: Individual feature branches.
    - *Source*: Created from `develop`.
- **hotfix/name**: Critical bug fixes.
    - *Source*: Created from `main`.
    - *Merge*: Into both `main` and `develop`.
- **release/vX.Y.Z**: release branches.
    - *Source*: Created from `develop`.
    - *Merge*: Into `main` and back into `develop`.

### Workflow

1.  **Start Feature**:
    ```bash
    git checkout develop
    git pull origin develop
    git checkout -b feature/my-feature-name
    ```
2.  **Commit**: Use Conventional Commits.
3.  **Push**: `git push origin feature/my-feature-name`
4.  **Pull Request**: Open PR to `develop`.

### Release Strategy

1.  Create `release/vX.Y.Z` from `develop`.
2.  Perform final testing and version bumps.
3.  Open PR to `main`.
4.  After merge, tag the release on `main`:
    ```bash
    git tag -a v1.0.0 -m "Initial production release"
    git push origin v1.0.0
    ```
5.  Merge `release/vX.Y.Z` back into `develop` to keep it up to date.

### Hotfix Flow

1.  Create `hotfix/issue-description` from `main`.
2.  Fix the critical bug.
3.  Open PRs to **both** `main` and `develop`.

## Commit Standards

We use [Conventional Commits](https://www.conventionalcommits.org/):

- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation only changes
- `style`: Formatting, white-space
- `refactor`: Code change that neither fixes a bug nor adds a feature
- `perf`: Performance improvement
- `test`: Adding/correcting tests
- `chore`: Build process, deps, etc.

**Example**: `feat: add user authentication login page`

## Pull Request Process

1.  **CodeRabbit Review**: Must pass automated review.
2.  **Manual Testing**: Describe manual tests in PR description.
3.  **Phase Progression**: ensure `todo.md` phase is complete.
4.  **Review**: Peer review required.

## Code Quality

- Keep frontend and backend loosely coupled.
- Write granular, self-documenting code.
- Avoid large, monolithic architectural changes without prior discussion.
