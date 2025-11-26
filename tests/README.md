# Lox Interpreter Test Suite

This directory contains comprehensive unit tests for the Lox interpreter implementation. The tests are organized into three main categories that mirror the implementation stages:

## Test Categories

### 1. Scanner Tests (`scanner.test.ts`)
Tests the lexical analysis phase, verifying that the scanner correctly tokenizes Lox source code.

**Covered test stages:**
- ✅ **RY8**: Empty file scanning
- ✅ **OL4**: Parentheses tokenization
- ✅ **OE8**: Braces tokenization  
- ✅ **XC5**: Single-character tokens (operators, punctuation)
- ✅ **EA6**: Lexical error handling
- ✅ **MP7**: Assignment & equality operators (`=`, `==`)
- ✅ **BU3**: Negation & inequality operators (`!`, `!=`)
- ✅ **ET2**: Relational operators (`<`, `<=`, `>`, `>=`)
- ✅ **ML2**: Division operator & comment handling (`/`, `//`)
- ✅ **ER2**: Whitespace handling
- ✅ **TZ7**: Multi-line error reporting
- ✅ **UE7**: String literal parsing
- ✅ **KJ0**: Number literal parsing
- ✅ **EY7**: Identifier parsing
- ✅ **PQ5**: Reserved word recognition

### 2. Parser Tests (`parser.test.ts`)
Tests the syntax analysis phase, verifying that the parser correctly builds Abstract Syntax Trees (ASTs).

**Covered test stages:**
- ✅ **SC2**: Boolean & nil literals
- ✅ **RA8**: Number literal parsing
- ✅ **TH5**: String literal parsing
- ✅ **XE6**: Parentheses grouping
- ✅ **MQ1**: Unary operators (`!`, `-`)
- ✅ **WA9**: Arithmetic operators - multiplication & division
- ✅ **YF2**: Arithmetic operators - addition & subtraction
- ✅ **UH4**: Comparison operators
- ✅ **HT8**: Equality operators
- ✅ **WZ8**: Syntax error handling

### 3. Interpreter Tests (`interpreter.test.ts`)
Tests the evaluation phase, verifying that expressions are correctly interpreted and evaluated.

**Covered test stages:**
- ✅ **IZ6**: Literal evaluation (booleans, nil, numbers, strings)
- ✅ **LV1**: String and number literal evaluation
- ✅ **OQ9**: Parenthesized expression evaluation
- ✅ **DC1**: Unary operators (negation `-`, logical not `!`)
- ✅ **BP3**: Arithmetic operators - multiplication & division
- ✅ **JY2**: Arithmetic operators - addition & subtraction  
- ✅ **JX8**: String concatenation
- ✅ **ET4**: Relational operators (`<`, `<=`, `>`, `>=`)
- ✅ **HW7**: Equality operators (`==`, `!=`)
- ✅ **GJ9**: Runtime errors for unary operators
- ✅ **YU6**: Runtime errors for binary operators (arithmetic)
- ✅ **CQ1**: Runtime errors for binary operators (addition)
- ✅ **IB5**: Runtime errors for relational operators
- ✅ **XY1**: Print statements
- ✅ **OE4**: Multiple statements
- ✅ **FI3**: Expression statements
- ✅ **YG2**: Variable declarations
- ✅ **SV7**: Variable runtime errors
- ✅ **BC1**: Variable initialization
- ✅ **DW9**: Variable redeclaration
- ✅ **PL3**: Assignment operations
- ✅ **VR5**: Block syntax
- ✅ **FB4**: Scoping
- ✅ **NE3**: If statements
- ✅ **ST5**: Else statements
- ✅ **FH8**: Else-if statements
- ✅ **XJ4**: Nested if statements
- ✅ **WK8**: Logical OR operator
- ✅ **JX4**: Logical AND operator
- ✅ **QY3**: While loops
- ✅ **BW6**: For loops
- ✅ **VT1**: Loop syntax errors
- ✅ **AV4**: Native functions
- ✅ **PG8**: Function declarations & calls
- ✅ **LB6**: Function arguments
- ✅ **PX4**: Function syntax errors
- ✅ **RD2**: Return statements
- ✅ **EY3**: Higher-order functions
- ✅ **FJ7**: Function runtime errors
- ✅ **BZ4**: Function scope
- ✅ **GG6**: Closures
- ✅ **VF4**: Class declarations
- ✅ **YK8**: Class instantiation
- ✅ **YF3**: Getters & setters
- ✅ **QR2**: Instance methods
- ✅ **YD7**: `this` keyword
- ✅ **DG2**: Invalid `this` usage
- ✅ **OU5**: Constructors
- ✅ **EB9**: Return from init
- ✅ **MF6**: Class inheritance
- ✅ **KY1**: Method inheritance
- ✅ **KA5**: Method overriding
- ✅ **AB0**: Inheritance errors
- ✅ **QI0**: `super` keyword
- ✅ **IB9**: Invalid `super` usage
- ✅ **DE8**: Identifier resolution
- ✅ **PT7**: Self-initialization errors
- ✅ **PZ7**: Variable redeclaration errors
- ✅ **EH3**: Top-level return errors

## Running Tests

### Run All Tests
```bash
# Using npm scripts
npm test
```

### Run Individual Test Suites
```bash
# Scanner tests only
npm run test:scanner

# Parser tests only  
npm run test:parser

# Interpreter tests only
npm run test:interpreter
```

## Test Structure

Each test case follows this structure:
```typescript
{
    name: "Descriptive test name",
    input: "source code to test",
    command: "./your_program.sh <command> test.lox",
    expectedOutput: "expected stdout output",
    expectedExitCode: 0, // or 65 for errors
    expectedStderr?: "expected error message" // optional
}
```

## Test Framework

The tests use a custom lightweight testing framework (`TestRunner`) that:
- ✅ Spawns the interpreter as a subprocess
- ✅ Writes test input to temporary files
- ✅ Captures stdout, stderr, and exit codes
- ✅ Provides detailed failure reporting
- ✅ Handles both success and error cases
- ✅ Supports parallel test execution
