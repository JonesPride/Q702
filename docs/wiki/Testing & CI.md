# Q702 — Testing & CI

## Available package commands
The root `package.json` defines:
- `npm run compile`: invokes `truffle compile`.
- `npm test`: placeholder script that prints “Error: no test specified” and exits with status 1.

## Verification status
The existence of a compile command does not establish that compilation currently succeeds. The test script is explicitly not implemented. This review did not run Truffle or deploy to a local or public chain.

## Required verification before deployment
1. Install dependencies using a lockfile-consistent package-manager workflow.
2. Run Truffle compilation and record the exact compiler/dependency versions.
3. Add contract tests for constructor parameters, owner-only minting, sequential token IDs, URI assignment, pause/unpause, transfer blocking while paused, burn behavior, enumeration, and voting checkpoints.
4. Test unauthorized callers for every privileged operation.
5. Test edge cases and revert behavior on a local chain.
6. Review compiler warnings and dependency vulnerabilities.
7. Keep deployment tests separate from mainnet deployment; never use real funds as a test substitute.

## CI status
No CI workflow or passing workflow run was verified during this documentation review. Do not claim that the contract is tested, audited, or deployment-ready.