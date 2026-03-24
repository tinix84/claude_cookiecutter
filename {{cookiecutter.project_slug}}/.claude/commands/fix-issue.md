# Fix Issue

Fetch the details of a GitHub issue and implement the fix.

## Context

Issue details:
```
!gh issue view $ARGUMENTS
```

Recent git log:
```
!git log --oneline -20
```

Current branch status:
```
!git status
```

## Instructions

1. Read the issue description above carefully.
2. Identify the files that need to change.
3. Make the minimal changes required to fix the issue.
4. Add or update tests to cover the fix.
5. Summarize what was changed and why.

Follow all rules in `.claude/rules/` when writing code.
