# ZK Sudoku Implementations

This project was developed as part of the [Zero Knowledge Proofs MOOC 2023](https://rdi.berkeley.edu/zk-learning/) from UC Berkeley RDI.

This repository contains three different implementations of Zero-Knowledge Proofs for Sudoku puzzles using different frameworks:

1. Circom
2. ZoKrates
3. Arkworks

## Dependencies

### Circom Implementation
* [circom](https://github.com/iden3/circom)
* [Node.js](https://nodejs.org/en/)
* [snarkjs](https://github.com/iden3/snarkjs)

### ZoKrates Implementation
* [ZoKrates](https://github.com/Zokrates/ZoKrates)

### Arkworks Implementation
* [Rust](https://www.rust-lang.org/)
* [ark-circom](https://github.com/gakonst/ark-circom)
* [ark-groth16](https://docs.rs/ark-groth16/)

## Project Structure

```
.
├── circom/
│   ├── sudoku.circom
│   └── sudoku.input.json
├── zokrates/
│   └── root.zok
└── arkworks/
    └── src/
        └── main.rs
```

## Instructions

### Circom Implementation
1. Navigate to the circom directory
2. Run `make verify` to execute the end-to-end verification
3. Check the Makefile for individual steps

### ZoKrates Implementation
1. Navigate to the zokrates directory
2. Compile the program: `zokrates compile -i root.zok`
3. Generate the proving key: `zokrates setup`
4. Compute the witness: `zokrates compute-witness -a <puzzle-inputs>`
5. Generate the proof: `zokrates generate-proof`
6. Verify the proof: `zokrates verify`

### Arkworks Implementation
1. Navigate to the arkworks directory
2. Build the project: `cargo build --release`
3. Run the tests: `cargo test`
4. Execute the proof generation: `cargo run --release`

## Files to Edit

### Circom
* `sudoku.circom`: The circuit template
* `sudoku.input.json`: The prover's input
  * The verifier's input (`sudoku.inst.json`) is computed from it

### ZoKrates
* `root.zok`: The main circuit implementation

### Arkworks
* `src/main.rs`: The main circuit implementation
