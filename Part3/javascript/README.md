# JavaScript Pattern Snippet & Tests

## Implemented Patterns
- **Currency Settlement Strategy**: Demonstrates strategy classes selected by `currencyStrategyFactory`, computing in minor units (cents) to avoid floating-point errors.
- **Transaction Completion Notification Observer**: Demonstrates callback listeners retained in an array and invoked in order by `NotificationPublisher`.

## Prerequisites
- Node.js (tested with Node.js v24.19.0).

## Execution and Test Command
From this directory (`Part3/javascript`):
```bash
node pattern_demos.js
```

## Test Fixture Assertions
The test runner executes 4 strict assertion checks:
1. `USD 10.00` to `EUR` at `0.92` produces `9.20`.
2. `EUR 10.00` to `EUR` produces `10.00`.
3. Unsupported currency pair throws Error (`unsupported pair`).
4. Observers log completion in exact sequence: `["email:t1", "audit:t1"]`.

Actual result: `4/4 passed`.
Process timing: Median duration over 5 runs is 63.374 ms (inclusive of Node runtime startup).
