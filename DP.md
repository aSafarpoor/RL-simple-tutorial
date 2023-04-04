# RL: Dynamic Programming

what we have?
* Value of state: $v_*(s)=max_a\sum_{s',r}p(s',r|s,a)[r+\gamma v_*(s')]$
* Value of an action in state: $q_*(s,a)=\sum_{s',r}p(s',r|s,a)[r+\gamma max_{a'}q_*(s',a')]$

Now with help of **DP**, we can calculate $V(s)$ too for each state, here update of bellman equation for this purpose is:
$V(S)=max_a\sum_{s',r}p(s',r|s,a)[r+\gamma V(s')]$

problem: we need to know state transition probability $p(s',r|s,a)$ which is not available without complete models and it is not possible in many tasks. DP solve it with using expected values instead of trial and error and using complete models.

DP algorithms:
1. Value iteration
2. p

## Value Iteration
In simple form we need to compute $\pi_*(s)$ based on $\pi_*(s)=argmax_a\sum_{s',r}p(s',r|s,a)[r+\gamma v_*(s')]$ but for this goal we need to know $v_*(s')$. We change formula to $V(S)=max_a\sum_{s',r}p(s',r|s,a)[r+\gamma V(s')]$.  In newer format, we know stimates of $V(s')$, and it is not eanough good in initialization step but it will improve step by step based on the rule.

![Algorithm](https://github.com/aSafarpoor/RL-simple-tutorial/blob/main/extra/dp%20alg%20vi.png)
![Output](https://github.com/aSafarpoor/RL-simple-tutorial/blob/main/extra/dp%20vi.png)
