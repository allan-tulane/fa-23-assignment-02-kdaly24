# CMPS 2200 Assignment 2

**Name:**______Killian Daly________

In this assignment we'll work on applying the methods we've learned to analyze recurrences, and also see their behavior
in practice. As with previous
assignments, some of of your answers will go in `main.py` and `test_main.py`. You
should feel free to edit this file with your answers; for handwritten
work please scan your work and submit a PDF titled `assignment-02.pdf`
and push to your github repository.


1. Derive asymptotic upper bounds of work for each recurrence below.
  * $W(n)=2W(n/3)+1$
.  
.  Leaf Dominated, as constant time in root is outpaced by leaf nodes. Number of nodes in tree determines upper bounds of work.  W(n) ∈ O(n^(log base 3(2)))
.  
.  
.  
  * $W(n)=5W(n/4)+n$
.  
Leaf dominated, as 5/f(b) == 5/4 > 1. W(n) ∈ O(n^(log base 4(5)))
.  
.  
.  
.  
  * $W(n)=7W(n/7)+n$
.  
.  Balanced, as 7/f(b) = 7/7 == 1 = 1. Upper bound is depth of tree * work per level, or logn * n.  $W(n) ∈ O(n\log n)$
.  
.  
.  
  * $W(n)=9W(n/3)+n^2$
.  
.  Balanced, as 9/f(b) = 9/3^2 == 1 = 1. $W(n) ∈ O(n^{2}\log n)$
.  
.  
.  
  * $W(n)=8W(n/2)+n^3$
.  
.  Balanced, as 8/2^3 == 1 = 1. $W(n) ∈ O(n^{3}\log n)$
.  
.  
.  
  * $W(n)=49W(n/25)+n^{3/2}\log n$
.  
.  Root dominated, as 49/f(b) = 49/((25^(3/2))log25) = 49/175 < 1. Knowing this, we only account for the cost of the root, making $W(n) ∈ O(n^{3/2}\log n)$
.  
.  
.  
  * $W(n)=W(n-1)+2$
.  
.  This is balanced as every level has the same constant cost, 2. As there are N levels, it is $W(n) ∈ O(n * 2)$
.  
.  
.  
  * $W(n)= W(n-1)+n^c$, with $c\geq 1$
.  
.  Similar to above, this is balanced with the same cost at each level. This is n levels times n^c, or $W(n) ∈ O(n^{c+1})$
.  
.  
.  
  * $W(n)=W(\sqrt{n})+1$
.  We can assume this is balanced, as it is only one tree with constant cost at each level. Depth of tree is log(n), with constant cost 1. $W(n) ∈ O(\log(\log n))$

2. Suppose that for a given task you are choosing between the following three algorithms:

  * Algorithm $\mathcal{A}$ solves problems by dividing them into
      five subproblems of half the size, recursively solving each
      subproblem, and then combining the solutions in linear time.
    
  * Algorithm $\mathcal{B}$ solves problems of size $n$ by
      recursively solving two subproblems of size $n-1$ and then
      combining the solutions in constant time.
    
  * Algorithm $\mathcal{C}$ solves problems of size $n$ by dividing
      them into nine subproblems of size $n/3$, recursively solving
      each subproblem, and then combining the solutions in $O(n^2)$
      time.

    What are the asymptotic running times of each of these algorithms?
    Which algorithm would you choose?
    
  Running times are as follows:

  $\mathcal{A}$ is $5W(n/2) + n$ , which means that W(n) ∈ O(n ^ (log base 2 of 5))

  $\mathcal{B}$ is $2W(n -1) + 1$ , which means that $W(n) ∈ O(2^{n})$

  $\mathcal{C}$ is $9W(n/3) + n^{2}$ , which means that $W(n) ∈ O(n^{2}\log n)$
    
  Given these runtimes, I believe that the best runtime depends on the input size N, and will differ between A and C. In a, log base 2 of 5 can be simplified to around 2.4, making $n^{2.4}$. However, for most sizes n (most above n = 3), A becomes the superior algorithm, and runs faster than both B and C. B, as it is exponential, will run longer than both A and C, and is not helpful. I would choose A


3. Now that you have some practice solving recurrences, let's work on
  implementing some algorithms. In lecture we discussed a divide and
  conquer algorithm for integer multiplication. This algorithm takes
  as input two $n$-bit strings $x = \langle x_L, x_R\rangle$ and
  $y=\langle y_L, y_R\rangle$ and computes the product $xy$ by using
  the fact that $xy = 2^{n/2}x_Ly_L + 2^{n/2}(x_Ly_R+x_Ry_L) +
  x_Ry_R.$ Use the
  stub functions in `main.py` to implement Karatsaba-Ofman algorithm algorithm for integer
  multiplication: a divide and conquer algorithm that runs in
  subquadratic time. Then test the empirical running times across a
  variety of inputs in `test_main.py` to test whether your code scales in the manner
  described by the asymptotic runtime. Please refer to Recitation 3 for some basic implementations, and Eqs (7) and (8) in the slides https://github.com/allan-tulane/cmps2200-slides/blob/main/module-02-recurrences/recurrences-integer-multiplication.ipynb
 
 


