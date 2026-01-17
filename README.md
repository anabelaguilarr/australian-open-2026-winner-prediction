# australian-open-2026-winner-prediction
Australian Open 2026 – Men’s Champion Prediction

This project applies machine learning and probabilistic simulation to estimate the men’s singles champion at the Australian Open 2026. The goal is to model match outcomes realistically and translate those predictions into tournament-level probabilities using the official draw.

Rather than predicting a single winner outright, the approach focuses on estimating match-level win probabilities and simulating the full tournament many times to reflect the uncertainty inherent in tennis competition.

Project approach

The model is built using historical ATP match data along with early 2026 results that occurred prior to the tournament. Player strength is represented through Elo ratings, with separate tracking for overall performance and hard-court performance. Recent form is incorporated using rolling performance windows to capture short-term trends.

All features are computed using only information available before each match, ensuring a leakage-safe setup that mirrors real-world forecasting conditions.

Match prediction and evaluation

A gradient boosting classifier is used to estimate the probability that one player defeats another. Each historical match is represented from both perspectives so the model learns relative strength rather than memorizing outcomes.

Evaluation is performed using an out-of-time split. Match-level accuracy is approximately 63–64%, while performance is primarily assessed using log loss and Brier score, which better reflect probability calibration for tournament simulation.

Tournament simulation

Using the official Australian Open draw, the trained model simulates the tournament thousands of times. Match winners are sampled based on predicted probabilities, and players advance through the bracket until a champion is produced.

Repeating this process produces a probability distribution over potential champions rather than a single deterministic outcome.

Players with limited historical data, such as qualifiers, are assigned neutral baseline ratings, which is standard practice and does not meaningfully affect championship-level results.

Results

Across simulations, the model identifies Jannik Sinner as the most likely men’s singles champion at the Australian Open 2026, followed by other top contenders including Novak Djokovic and Carlos Alcaraz.

<img width="665" height="470" alt="image" src="https://github.com/user-attachments/assets/66df577a-9563-4268-8e86-b87000130ed6" />

Predicted Tournament Outcomes

Champion 🏆
* Sinner J
  
Runner-up 🥈
* Alcaraz C
  
Semi-finalists
* Djokovic N
* Zverev A
  
Quarter-finalists
* Auger-Aliassime F
* Medvedev D
* Fritz T
* De Minaur A

The full pipeline, from data preparation to tournament simulation and visualization, is documented in the notebook included in this repository. Running the notebook from top to bottom will reproduce the results.
