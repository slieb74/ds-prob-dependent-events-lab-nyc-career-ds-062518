
# Dependent events

## Introduction

In the previous labs, events were mostly considered to be independent. In order to be ready for real world applications of probability, it is important to understand what happens when probabilities are not independent. Very often, the probability of a certain event depends on other events happening! Let's see how this all works in this lab.

## Learning objectives

In this lab, you'll learn 
- How to deal with probabilities when events are dependent
- about conditional probabilities
- how to calculate probabilities when events are independent


## Exercise 1

Let's reconsider the example where 2 dice are thrown. Given that at least one of the dice has come up on a number higher than 4, what is the probability that the sum is 8?

denote events A and B such that what we're looking for is the probability of B given A. 

### solution

Let $A:= \{(i,j) \in \Omega \mid \text{either i or j is 5 or 6}\}$, let $B:= \{(i,j)\in \Omega \mid i+j = 8\}$.

In total, there are 36 outcomes. $P(A) = \dfrac{20}{36}$. We want to know what the probability of B is given A, so $P(B \mid A)= \dfrac{P(B\cap A)}{P(A)}$. $B\cap A$ has 4 outcomes out of 36 (2 and 6, 3 and 5, 6 and 2, 5 and 2). This leads to:








```python
p_B_given_A = (4/36)/(20/36) 
p_B_given_A  # correct answer: 0.2
```




    0.19999999999999998



## Exercise 2

Let's go back to the credit card example. We worked on this exercise in the "probability via outcomes" lab. There we said that, at a supermarket, we randomly select customers, and make notes of whether a certain customer owns a Visa card (event A) or an Amex credit card (event B). Some customers own both cards.
You can assume that:

- P(A) = 0.5
- P(B) = 0.4
- both A and B = 0.25.


With the knowledge we have about conditional probabilities, compute and interpret the following probabilities:

- $P(B \mid A)$
- $P(B'\mid A)$
- $P(A\mid B)$
- $P(A'\mid B)$

### Solution

#### - $P(B \mid A)$

Probability of having an Amex credit card given that they have a Visa card

$P(B \mid A)= \dfrac{P(B\cap A)}{P(A)}$


```python
p_B_given_A = 0.25/0.5  
p_B_given_A # correct answer: 0.5
```




    0.5



#### - $P(B' \mid A)$

Probability of not having an Amex credit card given that they have a Visa card


```python
p_B_prime_given_A = 1 - 0.5
p_B_prime_given_A # correct answer: 0.5
```




    0.5



#### - $P(A \mid B)$

$P(A \mid B)= \dfrac{P(B\cap A)}{P(B)}$

Probability of having a Visa credit card given that they have an Amex card


```python
p_A_given_B = 0.25/0.4
p_A_given_B # correct answer: 0.625
```




    0.625



#### - $P(A \mid B')$

Probability of not having a Visa credit card given that they have an Amex card


```python
p_A_prime_given_B = 1 - 0.625 
p_A_prime_given_B  # correct answer: 0.375
```




    0.375



## Exercise 3

In Europe, except for regular gas, cars regularly run on Diesel as well. At a gas station in Paris, 40% of the customers fills up with Diesel (event G1), 35% with gas "Super 95" (event G2), and 25% with gas "Super 98" (event G3). Only 30% of the customers who buy Diesel fill their tank completely (event F). For "Super 95" and "Super 98", these numbers are  60% and 50% respectively.

- Compute the probability that the next customer completely fills their tank and buys Super 95.
- Compute the probability that the next customer completely fills their tank.
- Given that the next customer fills their tank completely, compute the probability that they bought Diesel. 

### Solution


$P(G1) = 0.4$, $P(G2)=0.35$, $P(G3) = 0.25$.

$P(F\mid G1) = 0.30$ , $P(F\mid G2) = 0.60$ , $P(F\mid G3) = 0.50$.


**Probability that the next customer completely fills their tank and buys Super 95.**

$P(G2\cap F) = P(G2)P(F\mid G2)$


```python
full_super_95 = 0.35*0.6
full_super_95 # correct answer: 0.21
```




    0.21



**Probability that the next customer completely fills their tank.**

We'll see this in the next lecture too, but in order to get to this, you basically need to sum over all the gas types.



$P(F) = P(G1\cap F)+P(G2\cap F)+P(G3\cap F)$


```python
full_diesel = 0.4*0.3
full_super_98 = 0.25*0.5

p_full = full_super_95 + full_diesel + full_super_98
p_full # correct answer: 0.455
```




    0.45499999999999996



**Given that the next customer fills their tank completely, compute the probability that they bought Diesel.**

$P(G1 \mid F) = \dfrac{P(G1 \cap F)}{P(F)}$


```python
p_diesel_given_full = (0.4*0.3)/p_full
p_diesel_given_full # correct answer: 0.263736
```




    0.26373626373626374



## Exercise 4

United airlines operates flights from JFK to Amsterdam, to Brussels and to Copenhagen. As you might know, flights are overbooked fairly often. Let's denote the probability of the flight to Amsterdam being overbooked equal to 40%, the probability of the flight to Brussels being overbooked equal to 25%, and the probability of the flight to Copenhagen to be overbooked being equal to 35%. 

- Compute the probability that all the flights are overbooked.
- Compute the probability of having at least one flight which is not overbooked.
- Compute the probability that exactly one flight is overbooked.

### Solution

The three events are independent!



**Compute the probability that all the flights are overbooked.**

$P(A\cap B \cap C) =  P(A)P(B)P(C)$


```python
p_all_overbooked = 0.25*0.40*0.35
p_all_overbooked # correct answer: 0.035
```




    0.034999999999999996



**Compute the probability of having at least one flight which is not overbooked.**


```python
at_least_one_not = 1-p_all_overbooked
at_least_one_not  # correct answer: 0.965
```




    0.965




```python
p_amsterdam = 0.4*0.75*0.65
p_brussels = 0.6*0.25*0.65
p_copenhagen = 0.6*0.75*0.35

p_just_one = p_amsterdam + p_brussels + p_copenhagen

p_just_one # 0.45
```




    0.45


