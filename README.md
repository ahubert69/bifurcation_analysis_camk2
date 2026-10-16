# bifana_camk2

Bifurcation analysis of CaMKII phosphorylation, based on the Graupner & Brunel (2007)
model of CaMKII auto-phosphorylation and PP1 dephosphorylation.

The model tracks the 13 phosphorylation states of the CaMKII holoenzyme as a linear
system driven by Ca²⁺ (via calmodulin) and PP1. Using
[BifurcationKit.jl](https://github.com/bifurcationkit/BifurcationKit.jl), the notebook:

- computes the steady-state phosphorylation level as a function of calcium,
- continues equilibria in `Ca` and `PP1` using pseudo-arclength continuation (PALC),
- detects bifurcations across a range of PP1 concentrations and plots the
  resulting branches.

## Contents

- `stability_camk2.ipynb` — parameter definitions, model equations (`mat_CamK2`, `F!`),
  and continuation runs for varying `PP1` values.

## Requirements

- Julia with the packages used in the notebook:

  ```julia
  using Pkg
  Pkg.add(["Statistics", "Revise", "Plots", "BifurcationKit", "LinearAlgebra"])
  ```

## Usage

Run the notebook top to bottom with IJulia / VS Code. The final cells produce the
bifurcation diagrams: CaMKII phosphorylation level versus calcium for each PP1 value.

## Reference

Graupner, M. & Brunel, N. (2007). *STDP in a bistable synapse model based on PKA and
CaMKII*. Biological Cybernetics.
