# australian-open-2026-winner-prediction
As a tennis player and data science graduate student, I wanted to combine on-court intuition with a rigorous, realistic modeling approach. Instead of predicting the champion directly, the project estimates match-level win probabilities and simulates the full tournament using the official draw.

The pipeline uses historical ATP match data to compute overall and hard-court–specific Elo ratings, along with recent performance indicators based on rolling match results. A gradient boosting classifier is trained using only pre-match information to avoid data leakage and ensure realistic evaluation.

To estimate title probabilities, the trained model is applied to the official Australian Open draw and the tournament is simulated thousands of times using Monte Carlo methods. The final output is a probability distribution over potential champions, along with a visualization of the top contenders.

This project emphasizes proper feature engineering, time-aware validation, and probabilistic reasoning, while remaining grounded in real tennis dynamics such as surface effects, form, and draw structure.
