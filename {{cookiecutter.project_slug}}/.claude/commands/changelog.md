# Generate Changelog

Generate a changelog entry for the latest set of commits.

## Context

Commits since last tag:
```
!git log $(git describe --tags --abbrev=0)..HEAD --oneline
```

Full diff since last tag:
```
!git diff $(git describe --tags --abbrev=0)..HEAD --stat
```

## Instructions

Generate a changelog entry in **Keep a Changelog** format for the commits above.

Group changes under:
- **Added** – new features
- **Changed** – changes to existing functionality
- **Deprecated** – soon-to-be removed features
- **Removed** – removed features
- **Fixed** – bug fixes
- **Security** – vulnerability fixes

Use today's date as the version date and suggest a semantic version bump (major/minor/patch).
