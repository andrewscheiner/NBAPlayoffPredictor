# 🏀 Box Score to Bracket  
### *Evaluating the Predictive Power of NBA Regular Season Performance on Playoff Outcomes*

> *"Can watching a few games tell you who’s making a deep playoff run?"*

---

## 📘 Overview

The NBA regular season packs 82 games per team—but how much of it truly predicts what matters most: the playoffs?

This project explores whether regular season performance, as captured by box score statistics, can forecast playoff outcomes. Using neural networks trained on small, game-by-game chunks (5–10 games at a time), we simulate how a fan or analyst might “learn” about a team’s postseason potential over time.

We aim to answer:
- Can we predict if a team will **make the playoffs**?
- Can we estimate how far a team will go—**1st round exit, Finals, or champions**?
- Are **later season games more predictive** than early ones?
- Does **game-by-game** vs **rolling averages** impact prediction quality?

---

## 📊 Data Collection

- **Source:** NBA.com (via `requests`, `pandas`, and [`nba_api`](https://github.com/swar/nba_api))
- **Data:**  
  - **Box scores (standard + advanced)** for every regular season game (1956–2024)  
  - **Playoff outcomes**: number of playoff wins per team
- **Preprocessing:** Aggregated team-level statistics over rolling 5–10 game chunks; engineered playoff outcome labels (missed playoffs, round exits, champions).

---

## 🧠 Model Architecture

We use a **neural network classifier** trained to predict playoff success based on regular season data segments.

### Core Experiments:
- **Sequential chunks** (mimicking watching games as the season progresses)  
- **Random chunks** (simulating selective viewing like a casual fan)  
- **Different window sizes** (5 vs 10 games)  
- **Custom models per team vs league-wide model**  
- **Raw games vs seasonal averages**

Our goal isn't just classification—it's to explore **how predictive value evolves over time**.

---

## 📈 Key Insights (So Far)

- Predictive accuracy **improves logarithmically** as more games are added.
- Certain teams show playoff trajectories **early**, others **mask their form** until later.
- Random sampling yields **less consistent predictions**, highlighting the value of watching games in order.
- Strong implications for **sports betting**, **season structure debates**, and **the play-in tournament**.

---