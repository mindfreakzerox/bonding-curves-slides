# Bonding Curves Slides

Reveal.js deck covering bonding curves and dynamic token pricing. Includes interactive Desmos graphs for each curve type so you can drag sliders live during class. Solidity examples are provided inline and in `/contracts`.

## Live Slides
- GitHub Pages: https://mindfreakzerox.github.io/bonding-curves-slides/

## Contents
- Why dynamic pricing and what bonding curves are
- Curve types: Linear, Exponential, Logarithmic, Sigmoid (S-curve)
- Interactive Desmos charts with sliders (parameters: slopes, offsets, growth rates, ceilings)
- Examples per curve (simple parameter presets)
- Solidity implementations per curve (compilable, see `/contracts`)
- Solidity building blocks (price function, integral for cost, events, security tips)
- Risks & gotchas (front-running, precision, liquidity drains)
- Resources: speedrunethereum guide, metana-bootcamp course style, Reveal.js docs

## Solidity Contracts
Contracts live in `/contracts`:
- `LinearBondingToken.sol` — community token, linear P = mS + b (no deps)
- `ExpoBondingToken.sol` — hype launch, P = a·e^{kS} (uses `prb-math` exp)
- `LogBondingToken.sol` — stabilizing, P = k·ln(S+c) (uses `prb-math` ln)
- `SigmoidBondingToken.sol` — soft cap, P = L/(1+e^{-k(S-S0)}) (uses `prb-math` exp)

> Note: Expo/Log/Sigmoid rely on PRBMathUD60x18. With Foundry: `forge install prb/math` and set remapping `prb-math=lib/prb-math/src/`. With Hardhat: `npm i prb-math` and import path `prb-math/PRBMathUD60x18.sol`.

The `costToMint` functions use discrete sums for clarity; for production, replace with analytic/approximated integrals and add spreads/fees and sell paths as needed.

## Dev Notes
- Single-page deck: `index.html` (includes CDN reveal.js + Desmos embed)
- No build step needed; edit `index.html` and push
- Pages is configured to serve from `main` branch root

## Usage
- Open the live slides link; use arrow keys or swipe to navigate
- On curve slides, move sliders to show how price reacts as supply changes

## License
- Educational/demo use. Adapt as needed.
