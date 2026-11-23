# Q702 — Testing & CI

## Available package commands
The root `package.json` defines:
- `npm run compile`: invokes `truffle compile`.
- `npm test`: placeholder script that prints “Error: no test specified” and exits with status 1.

## Existing contract tests
The repository contains `test/NFT.test.js` with five test cases:
- Contract name and symbol.
- Minting a token and storing/reading its URI.
- Token balance after minting.
- Transfer from the first account to a second account.
- Owner pause and unpause behavior.

The test file's existence does not prove that it currently passes. The configured development network points to `127.0.0.1:8545`; run a local Ganache CLI node and invoke `npx truffle test --network development` to execute the suite. This documentation review did not run the tests.

## Coverage gaps visible in the current test file
The current tests do not explicitly cover unauthorized mint/pause calls, transfer rejection while paused, sequential mint IDs beyond the first token, burn behavior, enumeration, voting checkpoints, malformed inputs, or edge-case revert behavior. Add focused tests before treating these areas as verified.

## CI status
No CI workflow or PR-triggered workflow run was found for the reviewed PR head commit. Do not claim that CI is green, or that compilation/tests passed, based only on the presence of a test file or package command.

## Required verification before deployment
1. Install dependencies using the lockfile-consistent npm workflow.
2. Run Truffle compilation and record compiler/dependency versions.
3. Run the existing local contract tests.
4. Add and run tests for the identified coverage gaps.
5. Review compiler warnings and dependency vulnerabilities.
6. Keep deployment tests separate from mainnet deployment; never use real funds as a test substitute.
7. Obtain an independent contract security review before handling real assets.