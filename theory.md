# Maximising Yield in Arbitrage Trading

## Introduction
Risk-free betting on the outcomes of football matches in betting markets can yield profit when conditions are favorable. Naive methods can be improved to reveal unobvious contract selections with better margins.

Consider the market "Team A Scores" with outcomes "Yes" and "No" priced at 20% and 80% respectively. Placing bets of size £10 and £50 respectively means that regardless of the outcome the net winning is £0. Now consider the exaggerated example where the outcomes are priced 10% and 80% respectively. Placing bets of size £10 and £20 mean in the case of a goal being scored $£10 \times 10 - £20 = £80$ is yielded. In the case of no goal being scored $£20 \times 1.2 - £10 = £14$. The sum of the odds is 90% despite the contracts covering all outcomes: one outcome will occur 100% of the time.

## Optimal Method
Consider the event which contains the potentially infinite set of all outcomes $O$. 
> In football, an event is a match and the set of outcomes is the set of all possible scores $\{(0,0), (0,1),...,(n,n)\}$.

A contract $c$ is a subset of outcomes $c_o \subseteq O$ with an associated cost value $c_c \subset \mathbb R^+$ which represents the price of the contract.
> In football, a contract could be "Team A Wins". The set of associated contracts $$c_o$ is all outcomes where Team A scores higher than Team B. For example $\{(1,0), (2,0),..., (m,n)\}, m > n$ The cost could be 10%.

The optimal opportunity in an event is the set of contracts $c_{1_o}, c_{2_o},...,c_{3_o}$ such that

$$ O \subseteq c_{1_o} \cap c_{2_o} \cap c_{1_o} \cap ... \cap c_{n_o} $$ 

and

$$ c_{1_c} + c_{2_c} + c_{1_c} + ... + c_{n_c} $$

is minimal. $O$ on the left-hand side of the subset indicates the potential for repeat outcomes on the right-hand side.
> In football, this could be the contracts "Over 1.5 Goals", "Exactly 0-0", "Exactly 1-0" and "Exactly 0-1" priced at 85%, 3%, 3% and 3% respectively, producing a total cost of 97 whilst covering all outcomes. 

## Optimal Solution
Then, we must determine the set of covering contracts with a minimal cost. This is the **Weighted Set Cover Problem** ([Weighted Set Problem](https://en.wikipedia.org/wiki/Set_cover_problem)), an NP-hard problem, making it unrealistic to solve as the potential number of contracts grows. Therefore, how the implementation chooses to approximate (or solve if the problem is sufficiently small) is unimportant.

With the optimal set of contracts obtained correctly sized stakes should be placed on each one.
