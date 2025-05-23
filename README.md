# Exploring-Mathematical-Near-Misses
(Fermat's Last Theorem Approximations &amp; Riemann-Zeta Zeroes)


# Overview 

[Link Document](https://people.math.harvard.edu/~elkies/ferm.html)

# 1. Fermat near-misses.

Fermat "near-misses" approximates the solution of x^n + y^n ~= z^n for all integers, with 0<x<=y<z<2^n in a given interval of n integers.

Extended from z<10^6 to z<2^23 = 8388608 with a threshold of the absolute value r = nz^(n-3)/(z^n - y^n - x^n) at 1 relative error threshold.

Heuristic suggests that for all n and r0, the number of solutions of |r|<r0 with z<N, should be asymptotically propotional to CnLog(N)/r0 where Cn is the area of Ln "circle" |x|^n + |y|^n < 1 and r<<z^0(1) holds for all n>3.

This is random though in some cases systematic families of solutions exceed random expectations.

One known family (2nt^n+1)^n -(2nt^n-1)^n with r = (3/(n-2)(n-1)) + O(t^-n) grows faster than expected but was below the threshold of |r|< 1.

# New polynomial families
a). Another family of (32t^9 + 6t)^8 + (32t^8 + 7)^8 with r = t^5/21 + O(t^−3) when n = 8. 

b). Whenever 3n(n−2) is a square,that is n=(2, 3,) 8, 27, 98, 363,... with the computation from 10^6 to 2^23 for (192t^8 + 24t^4 − 1)^4 − (192t^8 − 24t^4 − 1)^4 − (192t^7)^4, this yield r = −4t^4 + O(1) = (z/12)^(1/2) + O(1). 

This two gives rational curves on twisted Fermat hypersurfaces of degree n>4 in projective (n−2)-space.

# Key points 
- Finding "near-misses" is not random — special patterns exist.

- Certain values of n (like 8, 27, 98, 363...) have hidden families of near-misses based on deep number theory structure.

- The work shows how ancient math (Fermat's Last Theorem) can lead to new and surprising discoveries.

- Even though integer solutions (for n > 2) don't exist, near-misses tell a deeper story about how numbers behave.

# Python program (Fermat near-misses)
Python program that outputs near-misses of Fermat's Last Theorem based on the input n, c and a threshold level

Approach:
Brute-force search within a given range for a,b,c and n.

Check near-miss condition: Compute ∣a^n+b^n−c^n∣ and see if it's "small" relative to c^n.

Parameter tuning: Adjust thresholds for what counts as a "near-miss."

# How to run 
git clone https://github.com/Slozzyondul/Fermat-Near-Misses.git

cd Fermat-Near-Misses

python3 fermat_near_misses.py

# Terminal variables explanation
You will be prompted to input the variables based on your desired range 

n = to what power degree are you targeting must be greater than 2

c = maximum value (z^n)

relative error threshold = allowed relative error

Key in the name you want the results to be stored in at the parent folder of the project.



# 2. Riemann-Zeta Zeroes

To properly understand the Riemann-Zeta zeroes, we need to understand first the prime number theorem.

The prime number theorem approximates how many primes exists less than any given integer x. Since its an approximation, there exists an error because its not actual values.

Riemann hypothesis explores how big that error is.

Error term is related to Riemann-Zeta function when is equal to zero.

So, Riemann hypothesis concludes that the zeros of the Riemann-zeta function all lie on the line (1/2 + it) where it is the complex/imaginary part while 1/2 is the real part.

a.) Prime number theory by Gauss: pi(x) = represents the number of primes less than x.

Therefore, pi(x)/(x/log(x)) -> 1 as x -> infinity or pi(x) ~ x/log(x)

For instance, when x=100, pi(100) = 25 but 100/log(100) ~ 22 and when x=1000000000, pi(1000000000) = 50847534 but 1000000000/log(1000000000) ~ 48254942

This implies the error reduces proportionality when x is a large number.

b.) Dirichlet and Gauss approximation for pi(x) 

pi(x) ~ Li(x) =  ∫1/(log(x)) dt  at an interval of [2, x] where Li(x) is the logarthmic integral of x.

For instance, pi(1000000000) = 50847534 but Li(1000000000) = 50849234 which is more accurate approximation for pi(x).

# prime power counting function J(x)

J(x) = pi(x) + (1/2)pi(x)^(1/2) + (1/3)pi(x)^(1/3) + (1/4)pi(x)^(1/4) + ... 

Which leads to pi(x)= J(x) - (1/2)J(x)^(1/2) - (1/3)J(x)^(1/3) - (1/4)J(x)^(1/4) - ...

# Euler 
Euler was interested in harmonic series for instance 1+1/2+1/3+1/4+... diverges towards infinity.

Also, (1/1^x) + (1/2^x) + (1/3^x) + ... converges to a constant for all integers x except when x=1

This leads to ∑1/n^s = Π (p^s)/((p^s) -1) from n=1 to infinity = ((2^s)/(2^s)-1)((3^s)/(3^s)-1)((5^s)/(5^s)-1)... which is just an infinite product of primes.

So when s=2 we get (pi^2)/6 and when s=1 harmonic series

This means that there exists infinitely many primes numbers.

# Riemann-Zeta function
Riemann used Euler's function but applied a complex plane to it.

ζ(s) = ∑1/n^s from n=1 to infinity = Π (p^s)/((p^s) -1)  where s=w+it only when w>1 otherwise it diverges to infinity.

When w is a rational number, ζ(s) = ((2^s)(pi^s-1)sin((pi^s)/2)Γ(1-s)).ζ(1-s), so ζ(-1) = -1/12.

This means if zeta function is an extension of Euler's function then ∑1/n^-1 from n=1 to infinity ~ -1/12

Riemann-Zeta function has three parts where s is a real part

1.) ∑1/n^s from n=1 to infinity = Π (p^s)/((p^s) -1) when s>1

2.) (1-2^(s-1)^-1) ∑(-1^(n+1))/n^s from n=1 to infinity when 0<s<1 

3.) ((2^s)(pi^s-1)sin((pi^s)/2)Γ(1-s)).ζ(1-s) when s<0 we get trivial zero when s = 0,-2,-4,-6,...


From polynomial factorization for instance (x^3)+(2x^2)-13x+10 = (x-1)(x-2)(x+5) applying the same concept to zeta function we get

ζ(s) = (pi^(s/2))/(2(s-1)(Γ(s/2)-1))* Π(1-(s/p)) where p is non-trivial zeros.

Equate factorized zeta function to part 3 of zeta gives J(x) = Li(x)+∑Li(x^p) for all p - log(2) + ∫1/log(t)t((t^2)-1) dt from x to infinity.

This means J(x)~Li(x)

So the error term J(x)-Li(x) = ∑Li(x^p) for all p - log(2) + ∫1/log(t)t((t^2)-1) dt from x to infinity.

This implies zeta function has no zeros on the line  w=1 from s=w+it

Error term for prime numbers is controlled by the non-trivial zeros of zeta function.

Therefore, if Riemann hypothesis is true then error term has a bound |pi(x) - Li(x)| <= Csqrt(xlog(x))

Also, if Riemann hypothesis is true, there exist a similiar bound on two consective primes  Pn+1 -Pn <= CsqrtPnlog(Pn)


# Python program (Riemann-Zeta zeroes)
I have included a python program to demonstrate the sections using hard coded values but any value can be used.


# How to run 

git clone https://github.com/Slozzyondul/Fermat-Near-Misses.git

Install all the requirements

cd Fermat-Near-Misses

python3 riemann_zeta.py