---
title: Dueling Double Deep Q learning in intraday trading
tags:
  - Reinforcement Learning
  - Intraday trading
  - Rutgers MSMF
photos:
date: 2020-01-04 14:04:27
categories: Research & Projects
mathjax: true
---

![](http://wenchao4quant.oss-ap-southeast-1.aliyuncs.com/MFEassy/action.png)

"*Dueling Double Deep Q learning in intraday trading*", **Math 625 Portfolio Theory and Application Final Project**

**Keywords**: Reinforcement Learning; Intraday trading; US stocks

<!-- more -->

# **Purpose**

Training an agent use the DQN Dueling network and double Q value function in the custom environment ‘intraday’. The trained agent will use its ‘skill’ to submit trade action at every 390 steps in a day. Its performance is measured by ‘intraday’ environment and returned next step to the agent.

# **Approach**

- Dueling and double DQN model
    - Double Q value function is to remove the overestimate bias. The redefined loss functions:
$$ L_i(\theta_i) = \mathbb{E}_{s_{t},a_{t},r,s_{t+1} \sim D_i} [ (\mathbb{E}_{s_{t+1} \sim \mathcal{E}} [r_t + \gamma Q(\phi_{t+1}, \underset{a'}{\operatorname{arg max}}{Q}(\phi_{t+1}, a'|\theta_i)|\theta^{-})] - \gamma Q(\phi_t,a_t | \theta_i))^2 ]  $$
    - Dueling network separates Q network to two control layers: action dependent advantage function A and action independent value function V:
        $$ Q(\phi, a | \theta, \alpha, \beta) = A(\phi, a | \theta, \alpha) + V(\phi|\theta, \beta)$$
    - Adjustment: subtract an average advantage value of all action
        $$ Q(\phi, a | \theta, \alpha, \beta) = (A(\phi, a | \theta, \alpha) - \frac{1}{\# a'} \sum_{a'}^{} A(\phi, a'| \theta, \alpha)  ) + V(\phi|\theta, \beta) $$

![](http://wenchao4quant.oss-ap-southeast-1.aliyuncs.com/MFEassy/double_q.png)

- Environment ‘Intraday’ trading rules
    - The agent is can only execute 2 day-trades in these 390 steps. Day-trade is counted as a buy order and then followed by a sell order.
    - Each order will cost 0.5% transaction fee.
    - Buy order will always be executed at the high price of the current time step bar. Similarly sell order will always be executed at the low price of the current bar.
    - Sequence of order execution for 2 day-trades should be buy, sell, buy, sell. Buy order only submit when there is no buy order exists. Same, sell order cannot repeat twice since there is no stock hold at agent’s hand.
    - There is no overnight holding, all the remaining stock will be clear (sell) at the end by ‘intraday’ exchange. 

# **Data**

Symbols: 'AMP', 'INTC', 'AMZN', 'ANTM', 'T', 'AXP', 'ACN', 'ABC', 'UNH', 'WMT', 'APH', 'AMG', 'AEP', 'APD', 'ALLE', 'ARE', 'MA', 'PG', 'AIG', 'ALL', 'AEE', 'AWK', 'GE', 'MMM', 'PFE', 'WFC', 'ABT', 'ABBV', 'AES', 'AAP', 'AMT', 'CSCO', 'AME', 'AGN', 'APC', 'A', 'AAPL', 'VZ', 'ADS', 'BAC', 'CVX', 'AFL', 'JPM'

Fields: YYYY.MM.DD HH.MM.SS | OPEN | HIGH | LOW | CLOSE | VOLUME | NUMBER OF TRADES | WEIGHTED, AV. PRICE

Available data from [firstratedata](http://firstratedata.com/):

|      | symbols | Max date range  | Max time points  | Time range   |
|------|---------|-----------------|------------------|--------------|
| Hour | 486     | 2004.01-2019.03 | 7 hours bar/day  | 9:30 - 15:00 |
| Min  | 47      | 2004.01-2019.03 | 390 mins bar/day | 9:30 - 15:59 |


# **Slides**
{% pdf http://wenchao4quant.oss-ap-southeast-1.aliyuncs.com/MFEassy/rftrading.pdf %}

