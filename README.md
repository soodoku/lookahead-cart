# Lookahead CART

> Decision trees with bounded lookahead search

## Overview

Standard CART algorithms make greedy split decisions based only on immediate impurity reduction. This can miss globally optimal tree structures where a seemingly poor split enables much better future splits.

Lookahead CART uses bounded search with alpha-beta pruning to look ahead 2-3 levels when choosing splits, discovering tree structures that greedy methods miss.

## Code for LookAhead CART + Simulation Results

* [Lookahead CART](lookahead-cart.ipynb)

## Key Results

**XOR Regression Problem:**
- Standard CART (sklearn): MSE = 0.316
- Lookahead CART: MSE = 0.040 (**87% improvement**)
- Successfully discovers XOR interaction pattern

**Computational Cost:**
- 100-1000x time overhead vs standard CART
- 40-45% branch pruning effectiveness
- Memory overhead: ~100-150KB

## When It Works

✅ **Feature interactions** dominate individual feature effects  
✅ **Tree interpretability** is important  
✅ **Accuracy matters more than speed**  

❌ Simple linear relationships  
❌ Real-time applications  
❌ Large-scale production use (due to computational cost)


