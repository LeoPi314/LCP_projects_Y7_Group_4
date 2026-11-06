# Iterative Prisoner's Dilemma (IPD) Simulation

## Authors

* **Leonardo Pieripolli**


* **Tommaso Pirazzo**


* **Mattia Ponchio**


* **Benedetto Secco**



---

## Overview

This project explores the **Iterative Prisoner's Dilemma (IPD)** within the context of game theory. While the single-shot Prisoner's Dilemma dictates defection as the dominant strategy, repeating the interaction over multiple rounds often fosters the emergence of cooperative and altruistic behaviors.

This repository contains simulations, strategy implementations, and analytical tools to test how various behavioral algorithms perform against each other across different payoff matrices and round configurations.

---

## Tools & Libraries Used

The project was developed entirely in Python using a Jupyter Notebook environment, leveraging the following core libraries:

* **`numpy`**`: For matrix operations, linear algebra calculations.


* **`pandas`**: For data organization and structuring results.


* **`matplotlib` & `seaborn**`: For plotting match histories, score convergence, and visual analytics.


* **`itertools`: For handling state management and iterations.



---

## Implemented Strategies

The project features a diverse set of deterministic and probabilistic player strategies, each adhering to a standardized function template taking the round number, match history, and player index:

1. **NiceGuy**: Always cooperates.


2. **BadGuy**: Always defects.


3. **MainlyNice**: Randomly defects a small percentage ($k\%$) of the time.


4. **MainlyBad**: Cooperates a small percentage ($1-k\%$) of the time.


5. **RandomGuy**: Randomly chooses to cooperate or defect with equal probability (50/50).


6. **TitForTat**: Starts by cooperating, then mirrors the opponent's previous move.


7. **ResentfulGuy (Grim Trigger)**: Cooperates until the opponent defects once, then defects permanently.


8. **TrustingGuy**: Adapts its cooperation probability dynamically based on the opponent's historical cooperation rate.


9. **BalancingGuy (Thanos)**: Cooperates or defects depending on whether the cumulative history of cooperations is even or odd.


10. **MidResentful**: Cooperates usually, but defects if the opponent has defected in any of the last 3 rounds.


11. **ReverseTitForTat**: Defects on the first move, then plays the exact opposite of the opponent's last move.


12. **ScammingGuy**: Exploits a sequence (defect, then cooperate twice) and subsequently optimizes moves based on adversary behavior history.



---

## Core Structure & Mechanics

* **Payoff Matrix & Normalization**: The reward structure is governed by standard game theory parameters ($T > R > P > S$ and $2R > T+S$). Scores are normalized between $0$ and $1$ to allow fair comparisons across different payoff matrix configurations.


* **Rounds & Matches**:
* A **Round** executes a single 1v1 interaction, calculating immediate rewards via matrix multiplication.


* A **Match** runs a sequence of $N$ rounds, accumulating and normalizing scores dynamically over time.




* **Payoff Exploration**: Custom validation functions (`get_new_Payoff` and `test_parameters`) allow the simulation to test extreme and pathological game matrices (ranging from highly altruistic to highly competitive settings).
