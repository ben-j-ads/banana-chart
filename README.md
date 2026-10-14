# The Banana Chart

A single-page, dependency-free visualization of the negative binomial distribution of how many times buyers purchase a category.

Open `index.html` in any browser. No build step.

- **m** (mean purchases per buyer) and **r** (shape; smaller means more skewed) set the distribution.
- **Presets**: QSR, Bread, Automotive.
- **Readouts**: P(0), P(1), P(5+), and the share of purchase volume from buyers who bought once.
- **Brand overlay**: a green line showing a brand with a given penetration. Brand P(0) = 1 − penetration, and the remaining buyers keep the market's shape.

The distribution is P(X=k) = Γ(r+k) / (Γ(r)·k!) · (r/(r+m))^r · (m/(r+m))^k, computed with the recurrence P(k+1) = P(k) · (r+k)/(k+1) · m/(r+m), truncated once cumulative probability passes 0.9995.
