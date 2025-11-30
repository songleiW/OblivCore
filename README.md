# OblivCore: Oblivious Core Queries over Bipartite Graph Streams via Oblivious Message Passing

This repository contains the reference implementation of OblivCore, the first system for performing oblivious (α, β)-core queries over bipartite graph streams. 

Overview

Bipartite graphs are widely used to model relationships such as social interactions, e-commerce transactions, and financial activities. A core analytical task is the (α, β)-core query, which extracts a maximal subgraph where every upper-layer vertex has degree ≥ α and every lower-layer vertex has degree ≥ β.

# OblivCore enables such queries securely over distributed bipartite graph streams while preserving privacy. Our system builds upon a multi-server architecture and introduces new techniques for:
   •  Oblivious vertex degree computation via message passing.
   •  Reversed oblivious message passing to support secure out-degree computation.
   •  Oblivious low-degree vertex filtering using soft-filtering.

# Experimental results show that OblivCore outperforms generic MPC frameworks by up to 141× in query latency and 235× in communication cost.

Features
   •  Privacy-preserving (α, β)-core queries on bipartite graph streams.
   •  Efficient degree computation and filtering with oblivious message passing.
   •  Support for real-time stream updates with secret-sharing protection.
   •  Multi-server setting for distributed trust (tested with 3 servers).
   •  Evaluation on multiple real-world datasets (social, e-commerce, and network logs).
   
# Installation

# Requirements
   •  Python 3.9+
   •  MP-SPDZ or compatible MPC backend (if benchmarking)
   •  Required Python libraries:

pip install -r requirements.txt



Build

If OblivCore includes C++/MPC components, build them first:

make

Usage

Running OblivCore
   1. Prepare input bipartite graph streams (as edge lists).
   2. Define query parameters α, β, and time window size W.
   3. Run the system with:

python run_oblivcore.py --input data/graph.txt --alpha 5 --beta 3 --window 1000

Example

python run_oblivcore.py --input data/sample_edges.txt --alpha 5000 --beta 10 --window 10000

This will execute a (5000,10)-core query on the given stream snapshot.

Repository Structure

OblivCore/
├── src/                # Core implementation
│   ├── message_passing/  # Oblivious message passing algorithms
│   ├── degree/           # Oblivious degree computation
│   ├── filtering/        # Low-degree vertex filtering
│   └── utils/            # Helper functions
├── data/               # Example datasets
├── scripts/            # Running experiments and benchmarks
├── results/            # Experimental outputs
└── README.md           # Project documentation

License

This project is released under the MIT License (or specify your license).
