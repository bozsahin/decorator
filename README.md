# decorator
Python decorators, from functions with some arguments (d1), to composition (d2, d3), decorators with args (d4),
and fixpoint decorators (d5).

To use, just do in python (>= 3.8):

<code>from deco import * </code>

Decorator <code>d5</code> may need a bit of explaining. Lambda-calculus is easiest to describe it. 

I will use backslash for 'lambda'.

We can define factorial as a recursive function:

<code>fact = \n. if n>0 then n * fact(n-1) else 1</code>

We can abstract over the righthand side to avoid names in lambda-calculus.

<code> \f\n. if n>0 then n * f(n-1) else 1</code>

Now we get

(1) <code> fact= (\f\n. if n>0 then n * f(n-1) else 1)fact</code>

This is what <code>d5</code> does: <code>fact</code> is the fixpoint of <code>d5</code>.

Notice that 

<code> fact m = (\f\n. if n>0 then n * f(n-1) else 1)fact m</code> for any m,

therefore the equation (1) holds.

Can we write a decorator that fixes any function with a fixpoint? That's the combinator <code>Y</code>.
More on that later.

enjoy.
-cem bozsahin
