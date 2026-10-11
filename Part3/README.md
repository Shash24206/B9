# Cross-language comparison

The representative instances are **Currency Settlement Strategy** and **Transaction Completion Notification Observer**. They were selected because both remain significant after all Part 2 changes and exercise different variation mechanisms: a request-time algorithm choice and one-to-many event delivery. Each language implements the same fixture: convert USD 10.00 to EUR using 0.92, pass EUR through unchanged, and notify exactly two subscribers after completion.

Run from the language directory:

* Java: `javac PatternDemos.java && java PatternDemos`
* Python: `python pattern_demos.py`
* JavaScript: `node pattern_demos.js`
* C++: `g++ -std=c++17 pattern_demos.cpp -o pattern_demos && ./pattern_demos`

Java and C++ were not run in the supplied environment because their compilers were unavailable. The JavaScript and Python outputs are retained under `evidence/`.
