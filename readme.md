[sfold](https://github.com/tonyday567/sfold)
============================================

[![Build
Status](https://travis-ci.org/tonyday567/sfold.svg)](https://travis-ci.org/tonyday567/sfold)
[![Hackage](https://img.shields.io/hackage/v/sfold.svg)](https://hackage.haskell.org/package/sfold)
[![lts](https://www.stackage.org/package/sfold/badge/lts)](http://stackage.org/lts/package/sfold)
[![nightly](https://www.stackage.org/package/sfold/badge/nightly)](http://stackage.org/nightly/package/sfold)

`sfold` is a composable stream library

workflow
========

    stack build --test --exec "$(stack path --local-install-root)/bin/sfold-bench" --exec "$(stack path --local-bin)/pandoc -f markdown -i other/readme_.md -t markdown -o readme.md --filter pandoc-include --mathjax" --file-watch

performance benchmarks
======================

    machines                8.975e5 1.356e6 1.614e5 1.683e5 4.022e61.291e5 cycles
    pipe                    1.157e5 1.061e5 1.772e5 1.003e5 1.845e51.164e5 cycles
    pipe - state            1.711e5 2.877e5 1.394e5 2.389e5 1.388e51.455e5 cycles
    pipe - bad state        3.769e6 3.602e6 3.569e6 3.630e6 3.698e63.758e6 cycles
    foldl                   5.393e4 4.166e4 4.191e4 4.179e4 1.278e54.141e4 cycles
    pipe & skolems          1.046e5 2.057e5 9.190e4 2.095e5 9.180e49.205e4 cycles
    just a fold             3.626e4 2.653e4 2.735e4 2.703e4 2.722e42.433e4 cycles
