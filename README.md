# Crafting Interpreters (TypeScript)

A TypeScript implementation of the Lox tree-walk interpreter, faithfully adapted from [Crafting Interpreters](https://craftinginterpreters.com/) by Robert Nystrom.

This project is a port of the original Java implementation (jlox). You can find the original reference implementation here:
[https://github.com/britannio/lox/tree/main/jlox](https://github.com/britannio/lox/tree/main/jlox)

## Features

- Full implementation of the Lox language.
- Tree-walk interpreter architecture.
- Written in TypeScript for type safety and modern JavaScript features.
- Powered by the [Bun](https://bun.sh/) runtime for fast execution.

## Project Structure

- `app/`: Contains the source code for the interpreter (Scanner, Parser, Interpreter, Resolver, etc.).
- `lox-examples/`: A collection of Lox scripts demonstrating various language features.
- `tests/`: Test suite and test runner.

## Prerequisites

This project uses [Bun](https://bun.sh/). Make sure you have it installed on your machine.

## Installation

Install the dependencies:

```bash
bun install
```

## Usage

You can run the interpreter using the provided shell script or directly via Bun.

### Using the Shell Script

To run a Lox script file:

```bash
./your_program.sh run lox-examples/hello.lox
```

## Testing

The project includes a comprehensive test suite.

To run all tests:

```bash
bun run test
```

You can also run specific test suites:

```bash
bun run test:scanner
bun run test:parser
bun run test:interpreter
```
