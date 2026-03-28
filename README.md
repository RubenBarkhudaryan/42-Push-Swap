# 42 Push Swap

## Overview
Push Swap sorts a stack of integers using a limited set of operations while minimizing the number of moves.

The project includes:
- push_swap: generates sorting operations
- checker (or checker_linux): validates an operation sequence

This project is a constrained-operations optimization problem: correctness is mandatory, but performance is measured by operation count.

## Features
- Input validation:
  - integer format
  - duplicate detection
  - 32-bit range checks
- Stack operations:
  - sa sb ss
  - pa pb
  - ra rb rr
  - rra rrb rrr
- Optimized strategies for:
  - small stacks
  - larger datasets
- Bonus checker support

## Core Idea
Instead of directly sorting with normal algorithms, push_swap must sort using only the allowed stack operations. This forces algorithm design around operation economics.

Typical strategy split:
- small N: hardcoded or near-hardcoded optimal sequences
- larger N: indexing/chunking/radix-like approaches to reduce moves consistently

## Why Validation Is Critical
Input handling strongly affects reliability. The implementation validates:
- numeric format
- duplicates
- integer range
- edge cases such as empty or malformed argument combinations

On invalid input, the program should fail deterministically with the expected behavior.

## Build
- make

## Run
- ./push_swap 3 2 5 1 4

Check result:
- ./push_swap 3 2 5 1 4 | ./checker_linux 3 2 5 1 4

Quick benchmarking idea:
- generate random datasets
- count emitted operations
- compare against 42 scoring thresholds

## Project Structure
- src: main sorting and operation logic
- libft: shared helpers
- bonus: checker and bonus logic
- Makefile: build automation

Internal components usually include:
- parser/validator
- stack representation
- primitive operations
- sorting strategy controller

## Key Learnings
- Algorithmic optimization under operation constraints
- Data structure manipulation and indexing strategies
- Input safety and deterministic error handling

## Notes
Push Swap teaches how to balance algorithmic complexity and practical operation cost under strict rules.
