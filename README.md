# Reverse-an-Array-in-Java

Reverse an Array in Java
Here, in this page we will discuss the program to reverse an array in java. We are given with an array and need to print that array in reverse order. Here we will discuss different approaches to reverse the given input array.

Reverse an Array
Here, in page we will discuss various method for reversing the array. Different methods are :

Method Discussed
Method 1: Just print the array in reverse order
Method 2: Actual in-place reversing of the original array
Method 3: Recursive in-place reversing of the original array
 
Example :
Input : arr[5] = [10, 20, 30, 40, 50]
Output : Array after reversing, arr[5] = [50, 40, 30, 20, 10]
 
Method 1
Run an iterative loop from the last index of the array
Print each item one by one arr[i]
Method 1 : Java Code
Run
import java.util.Scanner;

public class Main
{
   public static void main(String args[])
   {

     int arr[] = {10, 20, 30, 40, 50};

     int n=arr.length;
     for(int i=n-1; i>=0; i--)
       System.out.print(arr[i]+" "); 
    }
}
Output:
50 40 30 20 10
Related Pages
Find Second Smallest Element in an Array

Calculate the sum of elements in an array

Sort first half in ascending order and second half in descending 

Sort the elements of an array

Finding the frequency of elements in an array

Method 2
Take two variables start=0 and end=n-1
Swap items at start & end indexes
Do start++ & end–
Stop when start & end indexes overlap one another
Print the array
 
Time and Space Complexity :
Time – Complexity : O(n)
Space-Complexity : O(1)
 
Reverse elements of an array in Java 2
Method 2 : Java Code
Run
import java.util.Scanner;

public class Main
{
  public static void main(String args[])
  {

     int arr[] = {10, 20, 30, 40, 50};

     int n=arr.length;
     int start = 0, end = n-1;
    
     while(start<end){
        int temp = arr[start];
        arr[start]=arr[end];
        arr[end]=temp;
        start++;
        end--;
     }
    for(int i=0; i<n; i++)
       System.out.print(arr[i]+" "); 
    }
 }
output :
50 40 30 20 10
Method 3
Initially pass values of start = 0, end = n – 1

Function gets called as reverseRecursive(arr, 0, len-1);
In each recursive iteration swap arr[start] & arr[end]
Make further recursive calls as reverseRecursive(arr, start + 1, end – 1);
return when (start >= end)
Print the array
Time and Space Complexity :
Time – Complexity : O(n)
Space-Complexity : O(n), require stack to store the recursive calls
 

Reverse elements of an array in Java
Method 3 : Java Code
Run
import java.util.Scanner;

public class Main
{
   static void reverseRecursive(int arr[], int start, int end)
   {
     if (start >= end)
        return;

      int temp = arr[start];
      arr[start] = arr[end];
      arr[end] = temp;

      // recursive call to swap arr[start+1] & arr[end-1]
      reverseRecursive(arr, start + 1, end - 1);
   } 
   public static void main(String args[])
   {

     int arr[] = {10, 20, 30, 40, 50};

     int n=arr.length;
     int start = 0, end = n-1;
     reverseRecursive(arr, start, end);

     for(int i=0; i<n; i++)
       System.out.print(arr[i]+" "); 
     }
 }
Output :
50 40 30 20 10
