# B9 - Quarkus Digital Wallet Pattern Case Study

This folder is the reproducible technical submission for **Design Pattern Identification and Evolution in a Quarkus-Based Digital Wallet Application**. The baseline is a deliberately small, self-contained Quarkus-style service model created for this case study; it is not claimed to be a production payment system.

## Team and Student Roster
Upload repository: `https://github.com/aswathymohan-amrita/23CSE455_DP_CaseStudy`  
Course: **23CSE455 - Design Patterns**  
Team: **B9**  

## Submission Metadata

| Item | Value |
| --- | --- |
| Team | B9 |
| Case Study Title | Design Pattern Identification and Evolution in a Quarkus-Based Digital Wallet Application |
| Application Source | Quarkus Reference Service Model (`Part1/code/digital-wallet` and `Part2/code/digital-wallet`) |
| Baseline Source Version | `baseline-local-2026-10-11` |
| Evolved Source Version | `evolved-local-2026-10-11` (CH01, CH02, CH03 applied) |
| Target Java Environment | Java 17; Quarkus 3.40.1; Maven 3.9+ |
| Persistence Model | In-memory repository for an isolated, inspectable pattern study |

## Inspected Modules & Scope
- **Baseline Scope (`Part1/code/digital-wallet`)**:
  - `com.b9.wallet.application.WalletFacade` (Facade pattern)
  - `com.b9.wallet.domain.Transaction` (Builder pattern)
  - `com.b9.wallet.domain.Money` (Value Object)
  - `com.b9.wallet.domain.Wallet` (Aggregate root)
  - `com.b9.wallet.notification.*` (Observer pattern: `NotificationPublisher`, `TransactionObserver`, `EmailNotifier`, `AuditNotifier`)
  - `com.b9.wallet.repository.WalletRepository` (Repository pattern)
  - `com.b9.wallet.transaction.*` (State pattern: `TransactionState`, `PendingState`, `CompletedState`; Command pattern: `TransferCommand`)
- **Evolved Scope (`Part2/code/digital-wallet`)**:
  - Replaces `WalletFacade` with evolved `WalletService` facade.
  - Replaces incremental `Transaction.Builder` with immutable record constructor.
  - Adds `CurrencyConversionStrategy`, `CurrencyStrategyFactory`, `VendorFxAdapter` (CH01).
  - Adds `PerTransferLimit` and `DailyLimitDecorator` (CH02).
  - Adds `FraudCheckChain`, `DenyListCheck`, and `VelocityCheck` (CH03).
  - Adds Quarkus REST endpoints (`WalletResource`) with CDI `@Inject` wiring and DTO records.

## Complete Folder Hierarchy
```text
23CSE455_DP_CaseStudy/
|-- B9/
|   |-- README.md
|   |-- B9_Report.pdf
|   |-- B9_Report.tex
|   |-- data/
|   |   |-- code                       # original application source
|   |   |-- test_result                # testcases, screenshot..etc
|   |   |-- patterns.csv
|   |   |-- pattern_counts.csv
|   |   |-- patterns_evolution.csv
|   |   |-- cross_language.csv
|   |   |-- llm.csv
|   |   |-- B9_Digital_Wallet_Dataset.xlsx
|   |-- Part1/
|   |   |-- patterns.csv
|   |   |-- Pattern_count.csv
|   |   |-- pattern_architecture       # diagram source + image
|   |   |-- Part1_prompt.txt
|   |   '-- llm.csv
|   |-- Part2/
|   |   |-- code/                      # evolved application source
|   |   |-- changes/
|   |   |   |-- Change1/               # requirement, diff, test result
|   |   |   |-- Change2/               # requirement, diff, test result
|   |   |   '-- Change3/               # requirement, diff, test result
|   |   |-- pattern_evalution.csv
|   |   |---- Pattern_count.csv
|   |   |-- diagrams                   # updated UML where needed
|   |   |-- Part2_prompt.text
|   |   '-- llm.csv
|   |-- Part3/
|   |   |-- Strategy/                  # repeat for each pattern type
|   |   |   |-- java/                  # snippet, test runner, README
|   |   |   |-- python/                # snippet, test runner, README
|   |   |   |-- javascript/            # snippet, test runner, README
|   |   |   '-- cpp/                   # snippet, test runner, README
|   |   |-- Observer/                  # repeat for each pattern type
|   |   |   |-- java/                  # snippet, test runner, README
|   |   |   |-- python/                # snippet, test runner, README
|   |   |   |-- javascript/            # snippet, test runner, README
|   |   |   '-- cpp/                   # snippet, test runner, README
|   |   '-- llm/
|   |       |-- part3_prompt.txt
|   |       |-- llm.csv
|   |       |-- pattern_crosslanguage.csv
|   |       '-- B9_slide.pdf
```


## Important Limitations
This reference study demonstrates design pattern identification, evolution, and cross-language mappings. It intentionally omits live external banking networks, distributed consensus, production encryption keyrings, PCI DSS certification, database transaction isolation levels, and monetary regulatory compliance.
