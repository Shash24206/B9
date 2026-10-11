# C++ Pattern Snippet & Tests

## Implemented Patterns
- **Currency Settlement Strategy**: Uses abstract base class `CurrencyConversionStrategy`, concrete derived classes (`SameCurrencyConversion`, `FixedRateConversion`), and polymorphic instantiation with `std::unique_ptr`.
- **Transaction Completion Notification Observer**: Uses `std::function<void(const std::string&)>` to register and invoke lambda observer callbacks.

## Prerequisites
- C++17 compliant compiler (`g++` or `clang++`).

## Compilation and Execution
From this directory (`Part3/cpp`):
```bash
g++ -std=c++17 pattern_demos.cpp -o pattern_demos
./pattern_demos
```

## Test Fixture Assertions
The `main()` routine verifies 4 assertions:
1. `USD 10.00` to `EUR` at `0.92` produces `9.20` EUR (verified with rounded minor cents).
2. `EUR 10.00` to `EUR` produces `10.00` EUR.
3. Unsupported currency pair throws `std::invalid_argument`.
4. Observers receive transaction `t1` and log `email:t1` followed by `audit:t1`.

Note: If no C++ compiler is present in the grading environment, this is marked `not_run: no compiler` per assignment guidelines.
