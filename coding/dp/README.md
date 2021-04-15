# DP

**Top down and Bottom up:** <br />
Recursion and iteration. <br />
````python
fib_cache = {}

def memo_fib(n):
  global fib_cache
  if n == 0 or n == 1:
     return 1
  if n in fib_cache:
     return fib_cache[n]
  ret = memo_fib(n - 1) + memo_fib(n - 2)
  fib_cache[n] = ret
  return ret

def dp_fib(n):
   partial_answers = [1, 1]
   while len(partial_answers) <= n:
     partial_answers.append(partial_answers[-1] + partial_answers[-2])
   return partial_answers[n]

print(memo_fib(5), dp_fib(5))
````
It seems like memorization is much more natural. You can take a recursive function and memorize it by a mechanical process (first lookup answer in cache and return it if possible, otherwise compute it recursively and then before returning, you save the calculation in the cache for future use), whereas doing bottom up dynamic programming requires you to encode **an order** in which solutions are calculated, such that **no problem is computed before the subproblems that it depends on**. <br />

