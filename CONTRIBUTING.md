# Contributing Guidelines

## Branching Strategy

We follow a strict Git flow:

- **main**: Production-ready code. Protected branch. Never push directly to main.
- **develop**: Integration branch. All features merge here first.
- **feature/name**: Individual feature branches.

### Workflow

1.  Checkout `develop`: `git checkout develop`
2.  Pull latest: `git pull origin develop`
3.  Create feature branch: `git checkout -b feature/my-feature-name`
4.  Commit changes.
5.  Push to origin.
6.  Create Pull Request (PR) to `develop`.

## Commit Standards

We use [Conventional Commits](https://www.conventionalcommits.org/):

- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation only changes
- `style`: Changes that do not affect the meaning of the code (white-space, formatting, etc)
- `refactor`: A code change that neither fixes a bug nor adds a feature
- `perf`: A code change that improves performance
- `test`: Adding missing tests or correcting existing tests
- `chore`: Changes to the build process or auxiliary tools and libraries such as documentation generation

**Example**: `feat: add user authentication login page`

## Pull Request Process

1.  **CodeRabbit Review**: All PRs must pass the automated CodeRabbit review.
2.  **Manual Testing**: Describe the manual testing steps performed in the PR description.
3.  **Phase Progression**: Ensure the current phase in `todo.md` is complete and tested before moving to the next.
4.  **Review**: At least one peer review is required before merging.

## Code Quality

- Keep frontend and backend loosely coupled.
- Write granular, self-documenting code.
- Avoid large, monolithic architectural changes without prior discussion.
