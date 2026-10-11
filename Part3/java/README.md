# Java Pattern Snippet & Tests

## Implemented Patterns
- **Currency Settlement Strategy**: Demonstrates strategy algorithm selection via `CurrencyStrategyFactory` and `CurrencyConversionStrategy` (`SameCurrencyConversion`, `FixedRateConversion`).
- **Transaction Completion Notification Observer**: Demonstrates event publication where `NotificationPublisher` holds `TransactionObserver` subscribers as lambda / functional expressions.

## Prerequisites
- Java Development Kit (JDK) 17 or higher (`javac` and `java`).

## Compilation and Execution
From this directory (`Part3/java`):
```bash
javac PatternDemos.java
java PatternDemos
```

## Test Expectations & Fixtures
The snippet executes four self-verifying test fixtures:
1. `USD 10.00` to `EUR` at fixed rate `0.92` converts to `EUR 9.20`.
2. `EUR 10.00` to `EUR` passes through unchanged (`EUR 10.00`).
3. An unsupported pair (`GBP` to `EUR`) throws an `IllegalArgumentException`.
4. Observers receive transaction `t1` and log completion notifications in strict sequence (`email`, then `audit`).

Expected output: `4/4 passed`.
Note: If JDK is not installed in the target environment, the result is recorded as `not_run: no JDK` per assignment instructions.
