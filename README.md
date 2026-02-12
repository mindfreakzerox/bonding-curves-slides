# Bonding Curves Slides

Reveal.js deck covering bonding curves and dynamic token pricing. Includes interactive Desmos graphs for each curve type so you can drag sliders live during class.

## Live Slides
- GitHub Pages: https://mindfreakzerox.github.io/bonding-curves-slides/

## Contents
- Why dynamic pricing and what bonding curves are
- Curve types: Linear, Exponential, Logarithmic, Sigmoid (S-curve)
- Interactive Desmos charts with sliders (parameters: slopes, offsets, growth rates, ceilings)
- Examples per curve (simple parameter presets)
- Solidity building blocks (price function, integral for cost, events, security tips)
- Risks & gotchas (front-running, precision, liquidity drains)
- Resources: speedrunethereum guide, metana-bootcamp course style, Reveal.js docs

## Dev Notes
- Single-page deck: `index.html` (includes CDN reveal.js + Desmos embed)
- No build step needed; edit `index.html` and push
- Pages is configured to serve from `main` branch root

## Usage
- Open the live slides link; use arrow keys or swipe to navigate
- On curve slides, move sliders to show how price reacts as supply changes

## License
- Educational/demo use. Adapt as needed.
