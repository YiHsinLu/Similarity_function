# Similarity_function
The paper "[Combinations of Jaccard with Numerical Measures for Collaborative Filtering](https://arxiv.org/ftp/arxiv/papers/2111/2111.12202.pdf)" show few similarity method. Those methods were very powerful and popular tools, so I decided make them into R functions. However it was not enough, maybe those function will become package in the future.

* $u_1$ and $u_2$ are two vectors in p-dimension space.
    + $u_1 = (r_{11}, r_{12}, \cdots , r_{1p})$
    + $u_2 = (r_{21}, r_{22}, \cdots , r_{2p})$
* $sim(u_1, u_2)$: similarity between $u_1$ and $u_2$.
* $sim(u_1, u_2) = 0$, if $|u_1|=0\;$ or $\;|u_2|=0$
* $sim(u_1, u_2) = 1$, if $r_{1k}=r_{2k}, \forall k=1,2,\cdots , p$

## Cosine Similarity

* $sim(u_1, u_2) = cosine(u_1, u_2) = \dfrac{u_1\cdot u_2}{|u_1||u_2|}$

## Triangle Area measure

* $u_1\cdot u_2\ge 0$ ; $sim(u_1, u_2) = TA(u_1, u_2) = $:
    + $\dfrac{(u_1\cdot u_2)^2}{|u_1|(|u_2|)^3}$, if $|u_1|\leq |u_2|$
    + $\dfrac{(u_2\cdot u_1)^2}{|u_2|(|u_1|)^3}$, if $|u_1|\> |u_2|$
* $u_1\cdot u_2\leq 0$ ; $TA(u_1, u_2) = TA(u_1, u_2) = $:
    + $\dfrac{u_1\cdot u_2}{(|u_2|)^2}$, if $|u_1|\leq |u_2|$
    + $\dfrac{u_2\cdot u_1}{(|u_1|)^2}$, if $|u_1|\> |u_2|$

## Pearson Correlation

* $sim(u_1, u_2) = pearson(u_1, u_2) = \dfrac{(u_1-\bar{u_1})\cdot (u_2-\bar{u_2})}{|u_1-\bar{u_1}||u_2-\bar{u_2}|}$