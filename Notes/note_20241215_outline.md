
# Introduction
## Motivation

## Literature Review

# Model

$$ V(s_t,\epsilon_t)=\max_{d\in D_t} u(d,s_t,\epsilon_t) + E[V(s_{t+1},\epsilon_{t+1})|s_t,\epsilon_t] $$

Market is defined by all the tickets from origin $o$ to destination $d$ a few days around the travel time (e.g. $\pm 3$ days).
- $d$: decision
- $s_t$: state
  - $p_t$: (dynamic) price
  - $\xi_t$: **difference** in my plan from the previous period
  - $x_1$: the number of connections
  - $x_2$: departure time
  - $x_3$：arrival time
  - $x_4$: option to modify/cancel/refund
- $\epsilon_t$: random shock 

Note:
- There's no consumption utility from each stage. The product is consumed/experienced at the end of the time horizon. 
- There's no discounting either.
- The agent incurs a loss if later on he needs to change the plan but can not.
- The agent experience a loss if later on he discovers the price has decreased but he has already purchased, or if later on he discovers the price has increased but he has not purchased.
## Binary choice $d$ and 4 time periods

### Period $t=1$
- if $d_t=1$, the agent's utility 
$$u(1,s_t,\epsilon_t)=-\alpha_1 p_t +\epsilon_t(1)$$
- if $d_t=0$, the agent's utility
$$u(0,s_t,\epsilon_t)=\epsilon_t(0)$$

### Period $t=2$
- if $d_t=1$, a price decrease will make me feel a loss. My plan changes a bit so that I want to change my flight (whether I can change depends on how flexible the ticket is). 

$$u(0,s_{t+1},\epsilon_{t+1})= - \gamma x_4 \xi_t + \epsilon_{t+1}$$
where $\xi_t$ is the difference in my plan from the previous period.

- if $d_t=0$, I can choose to buy or not in this period. If the price has decreased, I don't feel anything extra, if the price has increased, I feel a loss of having missed the opportunity.
  - if I choose to buy, $u(1,s_{t+1},\epsilon_{t+1})=-\alpha_1 p_{t+1}+\epsilon_{t+1}(1)$
  - if I choose not to buy, $u(0,s_{t+1},\epsilon_{t+1})=\epsilon_{t+1}(0)$
  
Question: should I take into account the price change (the difference $\Delta p$) in the utility function???

### Period $t=3$

Question: how do I model the shock to plan?

### Last period $t=4$

- if the agent holds a ticket and takes the flight, the utility is 
  $$X\beta+\epsilon_T$$
- otherwise, $\epsilon_T$
  
# Discussion
