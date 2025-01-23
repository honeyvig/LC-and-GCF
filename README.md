# LC-and-GCF
To find the LCM (Least Common Multiple) and GCD (Greatest Common Divisor) of two numbers in Python, we can implement both using basic Python functions.

Here’s a breakdown of both:

    GCD (Greatest Common Divisor): The greatest common divisor of two numbers is the largest number that divides both of them without leaving a remainder. A common method to compute the GCD is Euclid's algorithm.

    LCM (Least Common Multiple): The least common multiple of two numbers is the smallest positive integer that is divisible by both numbers. The relationship between GCD and LCM can be given by the formula:
    LCM(a,b)=∣a×b∣GCD(a,b)
    LCM(a,b)=GCD(a,b)∣a×b∣​

    This means you can calculate the LCM if you know the GCD of two numbers.

Python Code to Find LCM and GCD

import math

# Function to calculate GCD using Euclid's algorithm
def gcd(a, b):
    while b:
        a, b = b, a % b
    return a

# Function to calculate LCM using the relationship with GCD
def lcm(a, b):
    return abs(a * b) // gcd(a, b)

# Example usage
num1 = int(input("Enter the first number: "))
num2 = int(input("Enter the second number: "))

# Calculate GCD
gcd_result = gcd(num1, num2)

# Calculate LCM
lcm_result = lcm(num1, num2)

print(f"GCD of {num1} and {num2} is: {gcd_result}")
print(f"LCM of {num1} and {num2} is: {lcm_result}")

Explanation:

    GCD Function:
        The gcd function uses Euclid’s algorithm. The algorithm works by repeatedly finding the remainder when dividing the larger number by the smaller one until the remainder is zero. The last non-zero remainder is the GCD.

    Example:
    GCD(48,18)⇒48%18=12,18%12=6,12%6=0
    GCD(48,18)⇒48%18=12,18%12=6,12%6=0

    So, the GCD of 48 and 18 is 6.

    LCM Function:
        The lcm function uses the formula:
        LCM(a,b)=∣a×b∣GCD(a,b)
        LCM(a,b)=GCD(a,b)∣a×b∣​
        We multiply the numbers together and divide by their GCD to find the LCM.

    Example:
    LCM(48,18)=48×18GCD(48,18)=8646=144
    LCM(48,18)=GCD(48,18)48×18​=6864​=144

Example Output:

Enter the first number: 48
Enter the second number: 18
GCD of 48 and 18 is: 6
LCM of 48 and 18 is: 144

This code allows you to calculate both the GCD and LCM for any two numbers you input.
