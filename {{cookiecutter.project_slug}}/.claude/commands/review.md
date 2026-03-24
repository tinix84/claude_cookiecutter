# Review PR

Review the current pull request diff and recent test results, then provide structured feedback.

## Context

Current git diff:
```
${{ "{{" }} run: git diff main...HEAD {{ "}}" }}
```

Recent test output:
```
${{ "{{" }} run: {{cookiecutter.package_manager}} run test 2>&1 | tail -50 {{ "}}" }}
```

Open issues / TODO items added in this diff:
```
${{ "{{" }} run: git diff main...HEAD | grep -n 'TODO\|FIXME\|HACK' {{ "}}" }}
```

## Instructions

Review the diff above and provide feedback in the following format:

### Summary
One-paragraph description of what this PR does.

### ✅ Strengths
List what is done well.

### ⚠️ Concerns
List issues that must be addressed before merging (bugs, security issues, missing tests, broken conventions).

### 💡 Suggestions
Optional improvements that would be nice to have but are not blocking.

### Checklist
- [ ] Tests added / updated
- [ ] Documentation updated
- [ ] No secrets or credentials in diff
- [ ] Follows code-style and API conventions from `.claude/rules/`
- [ ] CI passes
