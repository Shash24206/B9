# Python Pattern Snippet & Tests

## Implemented Patterns
- **Currency Settlement Strategy**: Demonstrates duck-typed strategy classes selected by `currency_strategy_factory`.
- **Transaction Completion Notification Observer**: Demonstrates publisher maintaining list of callable observer functions and invoking them upon transaction completion.

## Prerequisites
- Python 3.10+ (tested with bundled Python 3.12.14).

## Execution and Test Command
From this directory (`Part3/python`):
```bash
python pattern_demos.py
```

## Test Fixture Assertions
The script runs 4 automated assertions:
1. `USD 10.00` to `EUR` at `0.92` produces `9.20`.
2. `EUR 10.00` to `EUR` produces `10.00`.
3. Unsupported currency conversion throws `ValueError`.
4. Observers receive transaction `t1` and verify recorded calls `["email:t1", "audit:t1"]`.

Actual result: `4/4 passed`.
Process timing: Median duration over 5 runs is 93.291 ms (inclusive of interpreter startup).
