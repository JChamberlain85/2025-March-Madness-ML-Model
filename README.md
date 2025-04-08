# 2025 NCAA March Madness Bracket Predictor – Neural Network Model

This project uses a neural network to predict the outcomes of the NCAA Men's Basketball Tournament by forecasting score margins between teams. It was designed to evaluate the feasibility of using machine learning for full bracket prediction based on historical team performance and season stats.

## Overview

- **Model Type:** Feedforward Neural Network (PyTorch)  
- **Objective:** Predict game score margins to simulate and auto-generate a complete March Madness bracket  
- **Training Data:** NCAA tournament and regular season results from 2021–2025  
- **Prediction Target:** Margin of victory (continuous regression)  
- **Bracket Name:** `picknroll_ml`  
- **Score:** 660 / 1920  
- **Percentile:** 22.9%  
- **Final Rank:** 19,590,728th out of 24+ million brackets


## Code and Architecture

The core model was implemented in PyTorch with a standard feedforward neural network design.

- **Input Features:** Team statistics (offensive/defensive efficiency, strength of schedule, win/loss margins, etc.)  
- **Target Variable:** Score margin between two teams  
- **Loss Function:** Mean Squared Error (MSE)  
- **Evaluation:** Accuracy on historical tournaments + bracket simulation for 2025  

## Performance by Round

| Round                  | Correct Pred | Matches  | % Accuracy |
|------------------------|--------------|----------|------------|
| Round of 64            | 20           | 32       | 62.5%      |
| Round of 32            | 9            | 16       | 56.25%     |
| Sweet 16               | 5            | 8        | 62.5%      |
| Elite 8                | 1            | 4        | 25%        |
| Final Four             | 0            | 2        | 0%         |
| National Championship  | 0            | 1        | 0%         |
| **Total**              | **35**           | **63**       | **55.56%**     |

## Notable Successes

Despite not scoring in the final rounds, the model correctly predicted several notable upsets and performed well in early rounds.

### Upsets Correctly Predicted

- **#9 Creighton over #8 Louisville**
- **#10 New Mexico over #7 Marquette**
- **#12 Colorado State over #5 Memphis**
- **#9 Baylor over #8 Mississippi State**
- **#11 Drake over #6 Missouri**
- **#10 Arkansas over #7 Kansas**
- **#12 McNeese over #5 Clemson**

## Compounding Errors and the Nature of March Madness

While my model performed exceedingly well compared against a random number genorator, I was overall disappointed and confused by the results. After the tournament I decided to retest my model one game at a time rather than asking it to predict 63 games all at once with no real results to compare to. The results of this test were extremely promising and have renewed my faith in my model's abilities.

| Round                  | Correct Pred | Matches  | % Accuracy |
|------------------------|--------------|----------|------------|
| Round of 64            | 20           | 32       | 62.5%      |
| Round of 32            | 13           | 16       | 81.25%     |
| Sweet 16               | 8            | 8        | 100%       |
| Elite 8                | 2            | 4        | 50%        |
| Final Four             | 2            | 2        | 100%       |
| National Championship  | 0            | 1        | 0%         |
| **Total**              | **45**           | **63**       | **71.43%**         |

This is a far better outcome and hilights the implications of getting an early pick wrong. Hopefully with another year's worth of data under its sleve, my model will perform even better next season.

## Comparison to Other Brackets

| Bracket                  | Points | Percentile | Type                 |
|--------------------------|--------|------------|----------------------|
| Human Picks              | 1290   | 85.6%      | Hand-selected        |
| **ML Model Iterative Picks** | **1260**    | **83.8%**  | **Neural Network**       |
| ESPN Auto Picks          | 1090   | 71.1%      | Algorithmic          |
| ChatGPT Picks            | 840    | 43.6%      | LLM-based logic      |
| **ML Model Picks**           | **660**    | **22.9%**      | **Neural Network**       |
| Random Picks             | 310    | 7.2%       | Pure RNG             |

## Conclusion

This project demonstrates the potential of machine learning—specifically neural networks—for modeling the unpredictable nature of March Madness. While the model fell short in the later rounds, it performed impressively in the early stages, correctly identifying several upsets and advancing mid-seed teams beyond expectations.

The results highlight both the promise and limitations of purely data-driven bracket prediction. Statistical trends can guide accurate forecasts in early matchups, but any error is compounded over time as matchups begin to look different than the model expects.

Nevertheless, this project validates that even a relatively simple neural network trained on historical data can outperform millions of random and less informed entries. With additional feature engineering, probabilistic modeling, and ensemble strategies, future iterations could push further into tournament accuracy.

This work serves as a foundation for future experimentation at the intersection of sports analytics and machine learning and I'm excited for next year's tournament.
