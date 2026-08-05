# Bug Fix Playbook

## Procedure

1. Reproduce or precisely define the failure.
2. Identify expected behavior and supporting evidence.
3. Locate the smallest responsible code path.
4. Add a failing regression test when practical.
5. Implement the smallest safe correction.
6. Run targeted and relevant broader tests.
7. Check for data, security, concurrency, tenancy, and compatibility impact.
8. Update status, checkpoint, affected docs, and release notes.

## Rules

- Do not hide symptoms with broad exception swallowing.
- Do not combine unrelated cleanup with the fix.
- Mark unverified production assumptions explicitly.
