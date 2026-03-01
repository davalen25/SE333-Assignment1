Part 1 — Boundary Analysis 
Quick definitions 
On-point: the boundary value where the condition just holds (true). 
Off-point: the nearest value just outside the boundary (false). 
When equality is involved, there are usually two off-points (one on each side). 
1. Multiple Choice (2%) 
A game has the condition: numberOfPoints <= 570 
Perform boundary analysis. What are the on/off points? Choose one and justify. 
A. On = 570, Off = 571 
B. On = 571, Off = 570 
C. On = 570, Off = 569 
D. On = 569, Off = 570’’ 

The condition is less than or equal to 570, so 570 is where the condition would hold true as 570 =570. The nearest value just outside the boundary would be 571 since 571 is not less than or equal to 570, so 571 evaluates to false.
2. Short Answer (1%) 
Perform boundary analysis on x == 10 . What are the on/off points? Explain briefly. 
		The on-point = 10
		Off-point =9 and 11
		10 would evaluate to true as it is the only value where the conditions holds true as 10=10. Both 9 and 11 are the off points as there are the nearest values on either side of the on point so they would evaluate to false.
3. Short Answer (2%) 
Postal codes in some imaginary countries are always composed of four numbers and two letters: for example, 2628CD (2%) 
Numbers in [1000, 4000] 
Letters in [C, M] 
SE333 - Assignment 1 (10%) - Specification Testing 1
Consider a program that receives two inputs; an integer (for the four numbers) and a string (for the two letters) and returns true (valid postal code) or false (invalid postal code) 
The boundaries for this program appear to be straightforward: 
Assumed boundaries: 
A. < 1000 : invalid 
B. [1000, 4000] : valid 
C. > 4000 : invalid 
D. [A, B] : invalid 
E. [C, M] : valid 
F. [N, Z] : invalid 
Task: Based on what you as a tester assume about the program, what other corner or 
boundary cases can you come up with? Describe these cases and how they may exercise the program based on your assumptions 

Integer boundary cases: 
999 & 4001: invalid
1000 & 4000: valid
	Corner cases:
2670 + CD: Valid
5000 + AB: Invalid
2000+ AB: Invalid
5000+CD: Valid
	
	The corner cases help verify that the program would correctly handle other cases like edge cases and combinations of valid or invalid cases.




Part 2 — Specification-Based Testing 
In Week 1, we started learning about specification-based testing. For this exercise, we will apply what we have learned to a new java class. Please go to D2L, open the NumberUtils.java file, and apply specification-based testing on it by following in the steps below: 
1. Understand the requirements 
Read NumberUtils.java : identify the method, its inputs, output, and behavior 
method : add(List<Integer> left, List<Integer> right)
inputs: Two lists of integers representing digits 0-9
output: List of integers representing the sum
Behavior: Adds two numbers, returns null if either input is null, empty list means 0, handles carry properly.


2. Identify input partition & boundary for each parameter: 
a. Individual input? 
Single digit: [0], [5], [9]
Invalid digits: [-1], [10], [15]
b. Combination of input? 
Both empty [0]
One empty, one non-empty,  return non-empty
c. Output? 
Single and multiple digit results


Part 3 — Bug Check 

The bug occurs when the method reverses the input lists using Collections.reverse(left) and Collections.reverse(right).
The method should not modify the input parameters
The input lists left and right should remain unchanged after the method executes
Only the result should be returned; the original inputs should be preserved
