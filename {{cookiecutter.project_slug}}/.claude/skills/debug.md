# Skill: Debug Error

## Description

Automatically invoked when the user pastes a stack trace, error message, or describes unexpected
behavior. Triggers on keywords like "error", "exception", "crash", "failing", "broken", "why
doesn't this work".

## Instructions

1. Parse the error message or stack trace to identify the exact file and line number.
2. Read the relevant source code around the reported location.
3. Form a hypothesis about the root cause.
4. Verify the hypothesis by tracing the execution path:
   - Check inputs and outputs at each step.
   - Look for off-by-one errors, null/undefined values, type mismatches, or unhandled async.
5. Propose the minimal fix that resolves the root cause without introducing regressions.
6. Suggest a test case that would have caught this bug.

Always explain **why** the bug occurred, not just how to fix it.
