# Kobe Bryant Hot Hand Analysis

## Overview

This project examines whether Kobe Bryant's shooting streaks during the 2009 NBA Finals provide evidence of the "hot hand" phenomenon.

Using R, I compare Kobe Bryant's actual shooting streaks with a simulated independent shooter who takes the same number of shots with a 45% shooting probability.

The goal is to explore whether Kobe's streak distribution looks meaningfully different from what we might expect if each shot were independent of the previous one.

## View the Analysis

- [Rendered HTML Analysis](Kobe-Bryant-Hot-Hand-Analysis.html)
- [RMarkdown Source Code](Kobe-Bryant-Hot-Hand-Analysis.Rmd)

## Research Question

Do Kobe Bryant's shooting streaks during the 2009 NBA Finals provide evidence of a hot hand, or are they consistent with the streak patterns of an independent shooter?

## Dataset

The analysis uses `kobe_basket`, a dataset containing 133 Kobe Bryant shot attempts from the 2009 NBA Finals.

Each observation includes information such as:

- Game
- Quarter
- Time
- Shot description
- Shot outcome

The `shot` variable records whether each attempt was a:

- `H` = Hit
- `M` = Miss

## Methodology

The analysis follows four main steps:

1. Calculate Kobe Bryant's actual shooting streak lengths.
2. Simulate 133 independent shot attempts using a 45% probability of making each shot.
3. Calculate the simulated shooter's streak lengths.
4. Compare the distributions of Kobe's streaks and the simulated shooter's streaks.

The analysis uses simulation to establish a baseline for what shooting streaks might look like when every shot is independent.

## Tools

- R
- RStudio
- tidyverse
- ggplot2
- openintro
- Probability simulation
- Exploratory data analysis

## Kobe Bryant Streak Distribution

Kobe's most common streak length was 0, meaning that many misses occurred without a preceding made basket in the streak definition used in the analysis.

His longest observed streak contained 4 consecutive made baskets.

## Independent Shooter Simulation

An independent shooter was simulated using:

- 133 shot attempts
- 45% probability of a made basket
- 55% probability of a missed basket

```r
shot_outcomes <- c("H", "M")

sim_basket <- sample(
  shot_outcomes,
  size = 133,
  replace = TRUE,
  prob = c(0.45, 0.55)
)
