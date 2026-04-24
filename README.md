# SWOOSH Benchmark Analysis

This repository contains an experimental evaluation of the SWOOSH NIKE scheme.

## Overview

The goal of this project is to analyze the performance and parameter selection of SWOOSH, a lattice-based non-interactive key exchange scheme.

## Contents

- Execution of the reference implementation
- Performance measurements:
  - Key generation (keygen)
  - Shared key derivation (skey_deriv)
- Comparison with reported results

## Environment

- WSL2 (Linux)
- Rust toolchain

## Source Code

```bash
Official implementation used for the experiments:  
https://github.com/MQuaresma/pswoosh  
([pswoosh repository](https://github.com/MQuaresma/pswoosh))


## How to run

```bash
cargo build --release
cargo run --release --bin bench_scheme

