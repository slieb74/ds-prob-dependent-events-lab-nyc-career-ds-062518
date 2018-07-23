
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

Denote the meaning of $A$, and of $B$.



```python
p_B_given_A = None
p_B_given_A  # correct answer: 0.2
```

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


```python
p_B_given_A = None
p_B_given_A # correct answer: 0.5
```

#### - $P(B' \mid A)$


```python
p_B_prime_given_A = None
p_B_prime_given_A # correct answer: 0.5
```

#### - $P(A \mid B)$


```python
p_A_given_B = None
p_A_given_B # correct answer: 0.625
```

#### - $P(A \mid B')$


```python
p_A_prime_given_B = None
p_A_prime_given_B  # correct answer: 0.375
```

## Exercise 3

In Europe, except for regular gas, cars regularly run on Diesel as well. At a gas station in Paris, 40% of the customers fills up with Diesel (event G1), 35% with gas "Super 95" (event G2), and 25% with gas "Super 98" (event G3). Only 30% of the customers who buy Diesel fill their tank completely (event F). For "Super 95" and "Super 98", these numbers are  60% and 50% respectively.

- Compute the probability that the next customer completely fills their tank and buys Super 95.
- Compute the probability that the next customer completely fills their tank.
- Given that the next customer fills their tank completely, compute the probability that they bought Diesel. 

### Solution


**Probability that the next customer completely fills their tank and buys Super 95.**


```python
full_super_95 = None
full_super_95 # correct answer: 0.21
```

**Probability that the next customer completely fills their tank.**

We'll see this in the next lecture too, but in order to get to this, you basically need to sum over all the gas types.




```python
None 
None

p_full = None
p_full # correct answer: 0.455
```

**Given that the next customer fills their tank completely, compute the probability that they bought Diesel.**


```python
p_diesel_given_full = None
p_diesel_given_full # correct answer: 0.263736
```

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
p_all_overbooked = None
p_all_overbooked # correct answer: 0.035
```

**Compute the probability of having at least one flight which is not overbooked.**


```python
at_least_one_not = None
at_least_one_not  # correct answer: 0.965
```

**Compute the probability that exactly one flight is overbooked.**


```python
None
None
None

p_just_one = None

p_just_one # 0.45
```
