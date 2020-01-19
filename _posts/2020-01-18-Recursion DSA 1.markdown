---
layout: post
title:  "Recursion in C++"
date:   2020-01-18 15:34:04 -0800
categories: recursion C++  datastructures
---
# What is Recursion?
	
Recursion is the process of a function repeatedly calling itself until it reaches an exit condition. It is incredibly useful both for prettier code and some data structures which thrive and require recursion. Recursion has some drawbacks such as the amount of the stack(memory) it takes. Before we approach that, it helps to have a fundamental undersanding of factorial. 

# What is factorial?
A factorial function offers a wonderful opportunity to understand and trace recursion without becoming overwhelmed by the idea.Briefly, factorial is notated by a number followed by exclamation point, meaning that number multiplied by each number less than it until it is <=1. Essentially, 4! is 4\*3\*2\*1.Other examples as follows.
- 2!= 2*1 
- 0!= 1
- 1!= 1

So now we have a understanding of factorial, lets jump into a function for recursion(written in C++)!

{% highlight C++ %}
int factorial(num)// A function for factorial. Takes and returns an integer.
{
if (num<=1) //Exit condition
	return num;
else
	return num*factorial(num-1);// Recursively calling the factorial function here. 
}

{% endhighlight %}
# Tracing
For simplicity of tracing, F1 is the original function, F2 is the second call of the function until F99(99th call of the function).
1. Attempting to trace this function with the number 3, we skip the first if statement and land at the else, arriving to 3*factorial(2).
Here the computer calls the function again. Here a couple things happen under the hood.**The current function(F1)pauses on the line return 3*factorial(2), while the function2(factorial(2)) becomes priority. 
After the function2(F2) finishes executing, function1(F1) resumes.**

2. So we continue with factorial(2), which again skips the if statement and runs the else statement leading to 2*factorial(1). **F2 pauses here and F3 begins**.

3. This time though, factorial(1) simply returns 1 back to the previous function(f2)**F3 finishes**.

4. F2 resumes at 2*1, which 1 was returned from F3. F2 returns the product,2. **F2 finishes**.

5. F1 resume at 3*2, which 2 was returned from F2. F1 returns the product 6 back to which function we imagined originally called it to run. **F1 finishes**.

# Conclusion
If you made it this far, congratulations. At this point you have some understanding of recursion.
![Man walking into room on fire](https://cdn.discordapp.com/attachments/219382924540248065/668253617937055806/unknown.gif)

It may feel intimidating or difficult still however with time and implementation, the difficulty will rapidly decline. The next step lies in both identifying recursive opportunities and implementation. 
# Further Learning

I highly recommend you spend time implementing Fibonacchi sequence, a simple search, exponent functions using recursion. Writing some of these both recursively and without recursion will benefit your understanding and usage of recursion. Later, if you identify a repetition of a certain process, it may be a good candidate for recursion.

# Resources 
If you would like the read more about recurison, here are some resources I used.

 
[C++ implementation of factorial](https://beginnersbook.com/2017/08/cpp-recursion/)


[More indepth resource but in Java](https://javascript.info/recursion)



