# Dependency maintenance validation

Updated runtime and development dependencies, the CI Ubuntu image, and the
Playwright Windows launch patch for playwright-core 1.64.1. Windows fixture PATH
handling uses native delimiters and one case-normalized PATH key. Doctor skill
requirements now match the shipped skill inventory. SDK test fixtures include
request IDs and handle nullable permission responses. The existing test type-debt
baseline shrank by 21 diagnostic identities; no new diagnostics were allowed.
HARNESS_VERSION is 6.

Validation (2026-10-17):

- Product typecheck and build passed. Optional CSO native build requires an
  unavailable MSVC 2022/Windows SDK installation.
- Test-code typecheck passed: 826 existing diagnostics, none new.
- Windows free suite: 14,752 passed, 396 skipped, one failed across 723 files.
  The failure was the offline CI-planner fixture's existing 15-second process
  timeout. Its isolated rerun passed all 16 tests. The aggregate run remains
  recorded as failed; its cause has not been conclusively established.
- After SDK fixture repairs, 230 focused Windows tests and 141 focused WSL tests
  passed. POSIX-only fixtures were verified under WSL; a preliminary unsupported
  Windows invocation failed on shell executable and file-mode assumptions.
- Paid live evaluations were not invoked. No test deadline or paid-case budget
  was increased, and no assertions were removed to obtain these results.
