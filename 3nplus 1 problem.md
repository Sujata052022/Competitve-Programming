# Competitive Programming
## 1. 3n+1 Problem 
**Aim:** 3n+1 Problem
### **Theory:**
<p>The 3n+1 Problem is known as Collatz Conjecture.
Consider the following operation on an arbitrary positive integer:
<ul><li>
If the number is even, divide it by two.
</li>
<li>If the number is odd, triple it and add one.</li></ul>
The conjecture is that no matter what value of the starting number, the sequence will always reach 1.
Observe that once it reaches 1, it will do like the following oscillation <br>
1 -> 4 -> 2 -> 1-.> 4 ->2 ....<br>
So, when it converges to 1, or does it?
So investigate the problem in certain details as much as possible with occasional exercises and some computer problems using any programming language.
<br> Let's start by playing with some numbers and observe what is happening actually.
<br>N=12    <&nbsp><&nbsp><&nbsp>  12 6 3 10 5 16 8 4 2 1
<br>N=22      <&nbsp><&nbsp><&nbsp>22 11 34 17 52 26 13 40 20 10 5 16 8 4 2 1
<br>N=3        <&nbsp><&nbsp><&nbsp>3 10 5 16 8 4 2 1
<br><br> Algorithm to generate a sequence of numbers:
<ul><li>
Start with an integer n. </li>
<li>If n is even, divide by 2. If n is odd, multiply by 3 and add 1.</li> 
<li>Repeat this process with the new value of n, terminating when n = 1. </li></ul>
<br>
It is conjectured (but not yet proven) that this algorithm will terminate at n = 1 for every integer n. Still, the conjecture holds for all integers up to at least 1, 000, 000. For an input n, the cycle-length of n is the number of numbers generated up to and including the 1. In the example above, the cycle length of 22 is 16. Given any two numbers i and j, you are to determine the maximum cycle length over all numbers between i and j, including both endpoints
<br>A piece of code:
<pre>
n = 12
print(n)
while n > 1:
    if n % 2 == 0 :
        n = n//2
        print (n)
    else:
        n = 3*n+1
        print (n)
    </pre>
    <br>
This will give the output:<br>
12 6 3 10 5 16 8 4 2 1<br>
Now depending on the input of "n", different sequences will be received.<br> 
Observe that different numbers requires different time to converge and that is the unpredictable which makes the problem so hard.
There are in total two possibilities:
<ul><li>
It may occur a particular value occurs repeatedly i.e. after some time the sequence starts repeating. We define the last non-repeating digit to be the Terminating Number. The total number of numbers in the sequence until the terminating number is called the Length of the Sequence. For eg: For 5 the Terminating Number is 1 and the Length of the sequence is 6.</li>
<li>We may never end the sequence. In that case, the sequence never terminates.</li></ul>

<br>
Exercise: Find out the length of the sequence for all the numbers from 1 to 100 by a computer program. Main task is to find a pattern among the numbers.
<pre>
c = 1
for n in range(2,101): 
	i = n 
	while i > 1:
		if (i % 2 == 0): 
			i = i//2 
			c = c + 1 
			if i == 1 : 
				print( "The length of the sequence of {} is {}".format(n, c) ) 
				c = 1 
		else: 
			i = 3*i+1 
			c = c + 1
</pre>
</p>
