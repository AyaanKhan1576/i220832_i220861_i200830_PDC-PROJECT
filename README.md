﻿# i220832_i220861_i200830_PDC-PROJECT
 
# Parallel Butterfly Computation in Bipartite Graphs

## Contributors
- **Ayaan Khan (22i-0832)** 
- **Ayaan Mughal (22i-0861)** 
- **Salar Shoaib (20i-0830)** 

## Overview
This project implements a parallel algorithm to count butterfly motifs in large bipartite graphs. The algorithm is based on the PARBUTTERFLY framework, adapted to leverage a hybrid parallelization approach using:

- **METIS** for partitioning the graph
- **MPI** for inter-node parallelism
- **OpenMP** for intra-node parallelism

Butterfly motifs are key building blocks in bipartite graphs and are important for understanding dense local structures, such as co-purchases, co-authorships, or collaborative tagging patterns.

## Features
- Scalable butterfly counting in large bipartite graphs
- Supports global butterfly counting, with optional tip/wing decomposition
- Hybrid parallelism using MPI + OpenMP
- Partition-aware computation using METIS

## System Architecture
```
      ┌────────────┐
      │  METIS     │
      └────┬───────┘
           ↓
 ┌─────────────────────┐
 │  MPI: Partitioned   │
 │  Processes          │
 └────┬─────┬─────┬────┘
      ↓     ↓     ↓
┌───────┐ ┌───────┐ ┌───────┐
│OpenMP │ │OpenMP │ │OpenMP │
└───────┘ └───────┘ └───────┘
           ↓
     MPI Reduce
           ↓
   Global Butterfly Count
```

## Acknowledgments
- Inspired by the paper: *"Parallel Algorithms for Butterfly Computations" by Jessica Shi and Julian Shun*
- METIS Library: [http://glaros.dtc.umn.edu/gkhome/metis/metis/overview](http://glaros.dtc.umn.edu/gkhome/metis/metis/overview)

## License
This project is released under the MIT License.

