# AGENTS Guidelines for This Repository

This repository contains a TON blockchain NFT development tutorial using Blueprint framework. When working on the project interactively with an agent (e.g. the Codex CLI) please follow the guidelines below for safe and efficient development.

## 1. Use Blueprint Commands for Development

* **Always use Blueprint CLI** for contract operations.
* **Test locally first** using the Sandbox before deploying to testnet.
* **Do _not_ deploy to mainnet** during agent development sessions.
* **Keep test wallets separate** from production wallets.

## 2. Keep Dependencies in Sync

If you update dependencies:

1. Use npm to manage packages: `npm install <package>`.
2. Run `npm update` to update existing packages.
3. Regenerate lock file with `npm install` after changes.
4. Verify compatibility with TypeScript and TON libraries.

## 3. Contract Development Workflow

Follow the Blueprint development flow:

1. **Build contracts**: Compile FunC contracts to BoC
   ```bash
   npm run build
   ```

2. **Test contracts**: Run Jest tests with Sandbox
   ```bash
   npm test
   ```

3. **Deploy contracts**: Use Blueprint scripts
   ```bash
   npm start
   ```

## 4. Code Quality Checks

Before completing any task, run these quality checks:

| Command               | Purpose                               |
| --------------------- | ------------------------------------- |
| `npm run build`       | Compile FunC contracts                |
| `npm test`            | Run contract tests                    |
| `npx prettier --write .` | Format TypeScript code             |
| `npx tsc --noEmit`    | Type check TypeScript files          |

## 5. Testing Guidelines

Test contracts progressively:

1. **Unit tests**: Test individual contract methods
2. **Integration tests**: Test NFT collection and item interactions
3. **Sandbox testing**: Simulate blockchain environment locally
4. **Testnet deployment**: Deploy to testnet with test TON

Never skip the testing phase before deployment.

## 6. Configuration Management

Configure network endpoints in `blueprint.config.ts`:

* Use testnet endpoints for development.
* Never commit API keys directly in config.
* Use environment variables for sensitive data.
* Verify endpoint connectivity before deployment.

## 7. FunC Contract Development

When modifying FunC contracts:

* Keep imports organized in `contracts/imports/`.
* Follow TON NFT standards (TEP-62, TEP-64).
* Use proper op-codes from `op-codes.fc`.
* Test gas consumption in Sandbox.
* Document custom functionality.

## 8. TypeScript Wrapper Development

When working with wrappers:

* Maintain type safety in all wrapper methods.
* Keep serialization/deserialization logic clear.
* Update compile configurations when contract changes.
* Test wrapper methods thoroughly.
* Use proper TON types from `@ton/core`.

## 9. Project Structure

Maintain the standard Blueprint structure:

```
contracts/     - FunC smart contract source files
wrappers/      - TypeScript wrapper classes
tests/         - Jest test suites
scripts/       - Deployment and utility scripts
```

## 10. Common Development Tasks

### Create New Contract
```bash
npx blueprint create NewContract
```

### Run Specific Test
```bash
npm test -- NFTCollection.spec.ts
```

### Deploy to Testnet
```bash
npx blueprint run
```

## 11. Useful Commands Recap

| Command                           | Purpose                          |
| --------------------------------- | -------------------------------- |
| `npm install`                     | Install dependencies             |
| `npm run build`                   | Build contracts                  |
| `npm test`                        | Run all tests                    |
| `npm start`                       | Run deployment script            |
| `npx blueprint create <name>`     | Create new contract              |
| `npx prettier --write .`          | Format code                      |

## 12. Safety Reminders

* **Never deploy untested contracts** to mainnet.
* **Use testnet TON** for all development testing.
* **Keep private keys secure** and never commit them.
* **Test gas optimization** to minimize fees.
* **Verify contract logic** before deployment.
* **Backup important data** before major changes.

## 13. TON-Specific Considerations

* Gas fees are paid in TON, ensure test wallet is funded.
* Contracts are immutable once deployed.
* Use proper error codes for contract failures.
* Follow TON standards for NFT metadata.
* Consider storage fees for NFT collections.

---

Following these practices ensures safe NFT development, prevents loss of funds, and maintains code quality. Always test thoroughly in Sandbox and testnet before considering any mainnet deployment.