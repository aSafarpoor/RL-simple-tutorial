
# RL: MDP

Author:  Ali Safaroor Dehkordi

**<S,A,R,P>**
* S $\rightarrow$ state
* A $\rightarrow$ action in each state
* R $\rightarrow$ set of rewards for each (s,a) pair
* P $\rightarrow$ $\bigvee_{i,j}^{} probability\ for\ s_i \rightarrow s_j$

Markov Chain: S,P

Markov Decision Process: S,P,A,R

classifications:
* Finite vs Infinite
* episodic vs continuing

**Trajectory$\tau$**
chain of $(S_i,A_i,R_i)$ 

**Discount Factor($\gamma$)**
$\gamma \in [0,1]$

**Return($G_t$)**

sum of rewards

$G_t = R_{t+1}+R_{t+2}+...+R_{T}$

$G_0 = R_{1}+R_{2}+...+R_{T}$

note: 
* $T$ is task completion time
* $R_t$: immidiate reward at time t

**goal:** maximize $E(G)$

**with $\gamma$:**

$G_0 = R_{1}+\gamma R_{2}+...+\gamma ^{T-1}R_{T}$

$G_t= R_{t}+\gamma R_{t+1}+...+\gamma ^{T-t-1}R_{T}$

**Values:**

state value: $v_{\pi}(s) = \mathbb{E}[G_t|S_t=s]$

action value: $q_{\pi}(s,a) = \mathbb{E}[G_t|S_t=s,A_t=a]$

##  Bellman Equations
**First Equation:**

$v_{\pi}(s) = \mathbb{E}[G_t|S_t=s]$

$=  \mathbb{E}[R_{t+1}+\gamma R_{t+2}+ ...+\gamma^{T-t-1} R_{T}|S_t=s]$

$=  \mathbb{E}[R_{t+1}+\gamma G_{t+1}|S_t=s]$

$=\sum_{a}\pi(a|s)\sum_{s',r}(s',r|s,a)[r+\gamma v_{\pi}(s')]$

**First Equation:**

$q_{\pi}(s,a) = \mathbb{E}[G_t|S_t=s,A_t=a]$

$=  \mathbb{E}[R_{t+1}+\gamma R_{t+2}+ ...+\gamma^{T-t-1} R_{T}|S_t=s,A_t=a]$

$=  \mathbb{E}[R_{t+1}+\gamma G_{t+1}|S_t=s,A_t=a]$

$=\sum_{s',r}\pi(s',r|s,a)[r+\gamma\sum_{a'}\pi(a'|s')q_{\pi}(s',a')]$




For practical phase, let's look as [MDP](https://github.com/aSafarpoor/RL-simple-tutorial/blob/main/codes/MDP.ipynb)


