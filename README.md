Factorial of a Large Number in Java
Today we will discuss the program to find the Factorial of a Large Number in Java. Factorial of a number means multiply of all below number with each other till 1. If user enter 0 or 1 , then factorial of both numbers will be 1 only.

Or If the user enters negative numbers then its factorial is not defined.
Example – 5! = 5*4*3*2*1 = 120

 

Factorial of a Large Number in Java
Method 1 :
 Initialize carry as 0.
Do following for i = 0 to res_size – 1
 Find value of res[i] * x + carry. Let this value be prod
 Update res[i] by storing last digit of prod in it.
 Update carry by storing remaining digits in carry.
Put all digits of carry in res[] and increase res_size by number of digits in carry.
factorial of large number
Run
public class Main
{
static void factorial(int n)
    {
        int res[] = new int[500];
 
        // Initialize result
        res[0] = 1;
        int res_size = 1;
 
        // Apply simple factorial formula
        // n! = 1 * 2 * 3 * 4...*n
        for (int x = 2; x <= n; x++)
            res_size = multiply(x, res, res_size);

        System.out.println("Factorial of given number is ");
        for (int i = res_size - 1; i >= 0; i--)
            System.out.print(res[i]);
    }
    static int multiply(int x, int res[], int res_size)
    {
        int carry = 0; // Initialize carry

        // One by one multiply n with individual
        // digits of res[]
        for (int i = 0; i < res_size; i++)
        {
            int prod = res[i] * x + carry;
            res[i] = prod % 10; // Store last digit of
                                // 'prod' in res[]
            carry = prod/10; // Put rest in carry
        }

        // Put carry in res and increase result size
        while (carry!=0)
        {
            res[res_size] = carry % 10;
            carry = carry / 10;
            res_size++;
        }
        return res_size;
    }

    // Driver program
    public static void main(String args[])
    {
        factorial(10);
    }
}
Output :
Factorial of given number is 
3628800
Related Pages
Given an array which consists of only 0, 1 and 2

Move all the negative elements to one side of the array

Find the Union and Intersection of the two sorted arrays

Find Largest sum contiguous Subarray

Minimize the maximum difference between heights 

Method 2 :
Big Integer can also be used to calculate factorial of large numbers.

 
Run
import java.math.*;
import java.util.*;

class Main {
public
  static void main(String[] args) {
   Scanner input = new Scanner(System.in);
   long n = input.nextLong();
  System.out.println(fact(n));
 }
public
 static BigInteger fact(long n) {
    BigInteger result = BigInteger.ONE;
     for (int i = 1; i <= n; i++)      
     result = result.multiply(BigInteger.valueOf(i));       
     return result;
 }
}
Output :
22
1124000727777607680000
