# DFS-Analytics-Project---NFL-WR-Props---Python

End-to-end pipeline that projects NFL wide receiver receptions, converts projections into O/U probabilities, and ranks props by expected value (EV) using PrizePicks-style payout structures (Power/Flex).

Data: nfl_data_py weekly stats, schedules, and play-by-play.

Features: rolling L3 targets/receptions/yards, catch rate, team target share, opponent pass defense, spread/total, home/away.

Modeling: Ridge/Lasso/RandomForest with season-wise GroupKFold.

2024 holdout: MAE 1.03 · RMSE 1.38 · R² 0.69.

Probabilities:

Normal approximation from residual dispersion.

Monte Carlo with negative binomial (over-dispersion for count stats).

Market merge: robust PrizePicks line fetch (retries/backoff), canonical F.Lastname name keys, team normalization, and merge audit (matched vs unmatched).

EV & ranking: computes p(Over), EV for Power/Flex, flags value plays, and exports tidy CSVs.
