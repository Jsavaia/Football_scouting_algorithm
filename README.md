# Football_scouting_algorithm

## Project Overview – Data-Driven Football Scouting

This project develops a data-driven scouting framework to identify football players
with high potential for upward career progression.

Using historical player-season data across multiple roles (defenders, midfielders,
and attackers), the objective is not traditional classification but ranking players
by their likelihood of progressing to a higher-tier league, replicating a real-world
scouting workflow.

Methodology Summary

Role-specific modelling
Defenders are split into central and lateral roles, with separate feature spaces and models trained for each role to reflect positional differences.

Binary target formulation
The target variable represents upward movement to a higher-tier league in subsequent seasons. The problem is framed as binary classification, but evaluated primarily through ranking metrics.

Modeling approach
Three models are evaluated per role:

Logistic Regression (interpretable baseline)

XGBoost (non-linear, high-capacity model)

MLP (supporting evidence)

Models are tuned using cross-validation and selected based on ranking performance, not raw classification accuracy.

Ranking-first evaluation
Instead of predicted class labels, players are ranked by predicted probability of upward movement. Performance is assessed using:

Hit@20

NDCG@20

ROC-AUC and F1 as secondary diagnostics

Final training and scouting output
The best-performing models are retrained on the full dataset and used to generate scouting tables, ranking all players by progression probability, percentile, and rank. Top-20 and Top-50 shortlists are produced for practical scouting use.

Interpretability
Model behavior is analysed using:

SHAP values for global and local explanations

Outcome

The result is a reproducible, interpretable scouting pipeline that mirrors professional decision-making: identifying high-potential players through probabilistic ranking rather than hard classification. The same methodology is designed to be extended to other positions (e.g. midfielders, attackers).
