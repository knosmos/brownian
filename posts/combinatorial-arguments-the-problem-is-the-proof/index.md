<!--
.. title: Combinatorial Arguments: The Problem is the Proof
.. slug: combinatorial-arguments-the-problem-is-the-proof
.. date: 2023-02-22 16:53:23 UTC-04:00
.. tags: 
.. category: math
.. link: 
.. has_math: true
.. description: 
.. type: text
-->

*The following is adapted from a lecture I gave to the PHS Math Team in February 2023*

A combinatorial proof shows that $A$ and $B$ are the same thing by showing that they are solutions to the **same counting problem**. Usually induction or algebraic proofs can also be used to solve these problems, but combinatorial proofs are usually more insightful and elegant.
<!-- TEASER_END -->

*Sidenote:* $\binom{n}{k}=\frac{n!}{k!(n-k)!}$ is the number of ways to choose $k$ things from a set of $n$ distinct things.

**Example 1.**
The $n$ members of Math Team want to visit the new Museum of Pigeon Holes, but there are only $k$ tickets left. How many ways are there to select $k$ people from the $n$ Math Team members?

**Solution 1.** We could solve this pretty easily with $\binom{n}{k}=\frac{n!}{k!(n-k)!}$. But notice this is the same thing as $\binom{n}{n-k}$, which is the number of ways to select the $n-k$ unlucky members. Because both $\binom{n}{k}$ and $\binom{n}{n-k}$ are both solutions to our problem, they must be equal to each other. In this case, we could have proved it algebraically, because $\binom{n}{n-k}$ is also equal to $\frac{n!}{k!(n-k)!}$. However, the algebraic justification does not give us an intuitive understanding of *why* they are actually equal.

**Example 2.**
Prove that $\binom{2n}{2}=2\binom{n}{2}+n^2$.

**Solution 2.** Formulate as the number of ways to choose a committee of $2$ from a population of $2n$ people. Then the left side is trivial. For the right side, suppose we split the people into two groups, each with $n$ people. Then the number of pairs is the number of ways to choose pairs within each group, which is $2\binom{n}{2}$, plus the number of pairs that go between the two groups, $n^2$.

**Solution 2, Algebraic.**
Left side:

$$\binom{2n}{2}=\frac{(2n)!}{2!(2n-2)!}$$
$$=\frac{2n\cdot (2n-1)}{2}$$
$$=\frac{4n^2-2n}{2}$$
$$=2n^2-n$$

Right side:
$$2\binom{n}{2}+n^2=2\frac{n!}{2!(n-2)!}+n^2$$
$$=2\frac{n\cdot (n-1)}{2}+n^2$$
$$=n^2-n+n^2$$
$$=2n^2-n$$

(see how much more intuitive the combinatorial argument is?)

**Example 3.**
(Vandermonde’s Identity, even though the Chinese discovered it 400 years earlier) Prove that
$$\binom{m+n}{r}=\sum_{k=0}^r\binom{m}{k}\binom{n}{r-k}.$$

*Hints:* Think of $m$ as the number of women and $n$ as the number of men.

**Solution 3.** Let's think about the problem of finding the number of ways to choose a committee of size $r$ from a population of $m$ women and $n$ men. Then the left side $\binom{m+n}{r}$ is the number of ways to choose $r$ people from $m+n$ total people.

For the right hand side, let $k$ be the number of women in the committee. If we fix $k$, then the number of committees is $\binom{m}{k}$, the number of ways to choose $k$ women, times $\binom{n}{r-k}$, the number of ways to choose $r-k$ men. So, the total is the summation of the product for over all $k$.

**The Binomial Theorem**

It's pretty famous:

$$(x+y)^n=\sum_{k=0}^{n}\binom{n}{k}x^ky^{n-k}$$

You could solve this with induction, but induction is tedious and I don't like it. How do we prove this with a combinatorial argument?

It's slightly different from the cases we have shown previously, but we can see that if we expand $(x+y)^n=(x+y)(x+y)\dots(x+y)$, each term is going to choose either $x$ or $y$ from each $(x+y)$ factor.

So what is the coefficient of the $x^ky^{n-k}$ term in the final result? Out of $n$ terms, we are choosing $k$ of the $x$s (and the rest will be $y$s), so the coefficient of $x^ky^{n-k}$ is $\binom{n}{k}$. You could think about it as the number of ways to arrange a string of $k$ letter $x$s and $n-k$ letter $y$s. For example, if $n=4$ and $k=2$, you have the strings

$$xxyy, xyxy,xyyx,yxxy,yxyx,yyxx$$

and indeed $\binom{4}{2}=6$. To get our final result, we take the summation over all $k$.

**So What?**

Through these examples, I hope the reason for combinatorial proofs has become clear - they allow you to get a deeper understanding of the problem you are solving, not just a proof through algebraic bashing. The symmetry of the these proofs by double-counting is, in my opinion, one of the most beautiful things about mathematics. 