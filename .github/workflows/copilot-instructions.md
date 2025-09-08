# Copilot Pull Request Review Instructions

You are reviewing a Pull Request. Evaluate the PR **rule-by-rule**, but also **go beyond the minimum**:
- If a rule is satisfied, still scan the diff for **any minor issues, edge cases, or style nits** related to that rule and add comments if possible.
- If there are multiple instances of an issue, report **each instance separately** as an inline comment.
- Do not limit yourself to one comment per rule: **the more relevant comments you can find, the better**.
- If a rule is satisfied everywhere, explicitly state **"No issues found"**.


## Rules
1. **Breaking Changes**: Verify no public API changes.
2. **Type Hints**: All functions have complete type annotations.
3. **Tests**: New functionality is fully tested.
4. **Security**: No dangerous patterns (eval, silent failures, etc.).
5. **Documentation**: Google-style docstrings for public functions.
6. **Code Quality**: `make lint` and `make format` should pass.
7. **Architecture**: Suggest improvements where applicable.
8. **Commit Message**: Follows Conventional Commits format.
9. Error Handling: Every fallible call checks and propagates errors with actionable messages.
10. Logging: Use the project logging API; no direct stdout/stderr; consistent levels.
11. Null/None Safety: Avoid nullable returns when a Result/Option-style is available.
12. Boundary Checks: All indexing, slicing, and pointer-like access guarded.
13. Resource Management: No leaks; files/sockets/handles closed in all paths.
14. Concurrency: No data races; lock order documented; avoid blocking on UI/main thread.
15. Performance: No N^2 hot paths; allocations in loops minimized; benchmarks where relevant.
16. I/O Robustness: Validate untrusted inputs; fail closed on malformed data.
17. Internationalization: No hard-coded user-visible strings without localization hooks.
18. Public API Stability: No breaking changes without proper deprecation window.
19. Deprecation: Deprecated APIs are documented with migration paths.
20. Feature Flags: New behavior behind flags/config; defaults maintain compatibility.

