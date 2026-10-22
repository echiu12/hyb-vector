Hybrid Bitvector with Rank and Select Queries
===

Description
---

[bitvector/hyb_vector.hpp](bitvector/hyb_vector.hpp) is a header-only
implementation of a hybrid bitvector that supports efficient rank and select queries.
It builds on [this](https://github.com/simongog/sdsl-lite/blob/master/include/sdsl/hyb_vector.hpp) hybrid bitvector implementation from [SDSL](https://github.com/simongog/sdsl-lite/tree/master).
In practice, it achieves excellent query times while also being highly space efficient.

Detailed descriptions and experimental results are given in the following papers:

    @inproceedings{kkp14dcc,
      author       = {Juha K{\"{a}}rkk{\"{a}}inen and
                      Dominik Kempa and
                      Simon J. Puglisi},
      title        = {Hybrid Compression of Bitvectors for the FM-Index},
      booktitle    = {Data Compression Conference, {DCC} 2014},
      pages        = {302--311},
      publisher    = {{IEEE}},
      year         = {2014},
      doi          = {10.1109/DCC.2014.87},
    }

    @inproceedings{ck26sea,
      author       = {Eric Chiu and
                      Dominik Kempa},
      title        = {Fast Select Queries Using Hybrid Bitvectors},
      booktitle    = {24th International Symposium on Experimental Algorithms, {SEA} 2026},
      series       = {LIPIcs},
      volume       = {371},
      pages        = {12:1--12:11},
      publisher    = {Schloss Dagstuhl - Leibniz-Zentrum f{\"{u}}r Informatik},
      year         = {2026},
      doi          = {10.4230/LIPICS.SEA.2026.12},
    }

The latest version of the hybrid bitvector with rank and select queries is
available at https://github.com/echiu12/hyb-vector.

Usage
---

To use this code, install [SDSL](https://github.com/simongog/sdsl-lite/tree/master)
and replace their [sdsl/hyb_vector.hpp](https://github.com/simongog/sdsl-lite/blob/master/include/sdsl/hyb_vector.hpp)
with our [bitvector/hyb_vector.hpp](bitvector/hyb_vector.hpp).
The `sdsl::hyb_vector` class should now support both rank and select queries.

Tests and Benchmarks
---

For tests and benchmarks, run:
```
./run.sh
```
The script requires:
- make
- cmake (to install SDSL)
- wget (to get text files)
- gunzip (to get text files)
- g++

The script will:
- Download text files into `files`.
- Load all necessary submodules.
- Install necessary libraries in `build`.
- Build and run `build/test_select`.
- Build and run `build/bench_plcp`, with the output written to `out/experiment_plcp.out`.
- Build and run `build/bench_bwt_select`, with the output written to `out/experiment_bwt_select.out`.
