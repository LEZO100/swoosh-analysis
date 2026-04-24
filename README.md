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

Official implementation used for the experiments:  
https://github.com/MQuaresma/pswoosh

## How to run

Executed in a WSL2 Linux environment:

cargo build --release
cargo run --release --bin bench_scheme

## Full Setup and Execution

The following steps describe how to fully set up the environment and execute the SWOOSH benchmarks from scratch.

### Requirements

- Rust (stable) and Cargo  
- GCC / build-essential  
- Linux environment (recommended: WSL2)

### Installation (Debian / Ubuntu / WSL2)

```bash
sudo apt update
sudo apt install -y build-essential
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
cd pswoosh-master/rust/ref0
cargo build --release
cargo run --release --bin bench_scheme
cargo run --release --bin bench_full
