# MScFE 652 — Module 6: Advances and Challenges in Factor Investing

Interactive companion to the M6 lessons, same format as the M3 and M5 apps.
Single self-contained `index.html`: no build step, no dependencies, no external
scripts or fonts. All computation runs client-side.

## Lessons covered

**1 · Profitable anomalies or anomalous profits**
A multiple-testing calculator: set how many factors the profession has tested and
how many genuinely work, then move the t-statistic hurdle and watch the false
discovery rate. Buttons snap to t = 1.96, t = 3.0, Bonferroni, and the hurdle that
holds false discoveries at 5%. Then a backtest-mining simulator where every
strategy has a true Sharpe of exactly zero — the best of 500 reliably looks
publishable, and the chart continues it into fresh data. Finishes with a
decomposition of a reported return into statistical bias, post-publication
arbitrage, and costs.

**2 · Smart beta, herding, and not-so-smart beta**
A crowding feedback loop — performance draws flows, flows move prices, prices
raise today's return and lower tomorrow's — run over 20 quarters, reporting the
gap between the buy-and-hold return and the return earned by the average dollar.
Then a 300-stock universe where a naive value screen is inspected for the
momentum, size, beta and sector bets it picked up by accident, with
sector-neutral and residualised sorting as alternatives.

**3 · Factor models with machine learning**
A ridge path on simulated returns showing in-sample fit rising monotonically
while out-of-sample fit peaks and falls, with least squares going negative once
predictors per observation get large. Then a true model with an interaction term,
fitted three ways — plain linear, linear with interactions, and a depth-limited
regression tree — with the predicted surface drawn for each. Closes with the
fundamental law of active management translating a fraction-of-a-percent R² into
a net information ratio.

**4 · Advanced factor construction**
A construction lab over seven choices (universe, quantile cut, rebalance
frequency, weighting, neutralisation, outlier handling, data lag). All 972
combinations are enumerated so the histogram behind your configuration is every
result you could equally well have reported. Then signal combination: optimal
versus equal weights as signals converge, and integrated versus blended
portfolios tested on matched terms.

## Numerical methods used

- Normal CDF/quantile: Abramowitz–Stegun erf, Acklam inverse
- Ridge regression: centred cross-products, Gauss–Jordan inverse, refitted across a 24-point log penalty grid
- Regression tree: greedy CART with depth and minimum-leaf limits
- Correlated draws: Cholesky with a seeded Mulberry32 / Box–Muller generator
- Signal combination scored over 200 independent cross-sections, since one draw cannot rank the methods

## A note on one result

The signal-combination panel does not reproduce the usual claim that integrating
signals beats blending portfolios. On a clean linear data-generating process the
two come out level. The copy says so, and explains where the real-world advantage
actually comes from — trading costs and nonlinear factor interaction, neither of
which this model contains. The combination gain that does show up strongly is the
other one: weighting several imperfectly correlated signals beats picking the best.

## Publishing

Rename to `index.html`, push to the repository root, enable GitHub Pages on that
branch — same as the previous modules.
