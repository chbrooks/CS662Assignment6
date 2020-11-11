### Assignment 6: Uncertainty

#### Due 11/22 at 11:59pm


This assignment consists of two parts: a set of written questions, and
a programming assignment. For the written portion, please add a
document to your repository containing the
answers. Word, PDF or ASCII text are acceptable formats. 

1 - (10%) Suppose that we are trying to decide whether to
  play a game. Playing the game costs $1. There are four outcomes:
   - 1/3 of the time we will win $2 
   - 1/20 of the time we will win $10
   - 1/1000 of the time we will win $5000 
   - and the rest of the time we will win nothing. (the outcomes are mutually exclusive.)

What is the expected utility of this game? Should we play?

 2 -  Suppose that our route-finding agent is trying to suggest a route for
us to get from USF to Oakland. We want to minimize the expected travel
time. We know that, when the Bay Bridge is busy, it takes 1 hour to
drive there, and when the Bay Bridge is not busy, it takes 30 minutes
to drive there. We know that taking BART always takes 40 minutes. We
also know that the Bay Bridge is busy 40% of the time. 

a. (5%) Without any other information, should we drive or take BART? Show all necessary work. 

b.(10%) Suppose that we can spend five minutes checking a traffic website to see if the bridge is actually busy. 
We know that 90% of the time when the bridge is actually busy, the site will say
it's busy. (P(site | busy) = 0.9) We also know that 20% of the time
the site will say the bridge is busy when it actually isn't. (P(site |
!busy) = 0.2) 

c. (5%) Use Bayes' rule to determine the probability that the bridge is
actually busy if the site says it is. (P(busy | site)). 

d. (10%) Use a value of information calculation to determine whether it is worth it for us to spend five minutes 
checking the traffic website. 

 Markov Decision Processes.  For this problem, you will implement
the value iteration and policy iteration algorithms. I've provided a
representation for states, a map, and the setup for two problems - the
one shown in R&N (and done in class), and a larger problem, the map of
which can be found in the file p2.jpg. In this second problem, the
agent moves in the intended direction with P=0.7, and in each of the
other 3 directions with P=0.1.

Your task is to implement the value iteration and policy iteration algorithms and 
verify that they work with both problems. (I'd suggest doing the R&N problem first.) 

(20%) Implement the value iteration algorithm.

(20%) Implement the policy iteration algorithm.

Here's an example of what the code looks like running in the Python
interpreter with gamma=0.8, r=-0.04 and error=0.0001:
<pre>
>>> import mdp
>>> m = mdp.Map()
>>> m.getMapFromFile("rnGraph")
>>> m.valueIteration()
>>> [(s.coords, s.utility, s.policy) for s in m.states.values()]
>>> [(s.coords, s.utility, s.policy) for s in m.states.values()]
[('11', -1.0, None), ('10', 1.0, None), ('1', 0.36897400368491667, 'right'), ('3', 0.73239206253199807, 'right'), ('2', 0.55800509251153152, 'right'), ('5', 0.42253248924235004, 'up'), ('4', 0.28095459542448692, 'up'), ('7', 0.2270923185711371, 'right'), ('6', 0.21512107599383087, 'up'), ('9', 0.12044027474165538, 'left'), ('8', 0.29822340058012747, 'up')]
</pre>

 (20%) Q-learning.  Complete the implementation of
  Q-learning provided in your repository. Most of the code is there
  for you; you need to complete update().
