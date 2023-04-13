# Lab-7_202001106

HARDI SANGHANI
202001106

Section A:
Consider a program for determining the previous date. Its input is triple of day, month and year with the following ranges 1 <= month <= 12, 1 <= day <= 31, 1900 <= year <= 2015.The possible output dates would be previous date or invalid date. Design the equivalence class test cases?

Answer: 
Equivalence Classes:- 
1. Months are less than 1. 
2. Months are between 1 and 12.
3. Months are greater than 12.
4. Day is less than 1. 
5. Day is between 1 and 31. 
6. Day is greater than 31. 
7. Year is less than 1900. 
8. Year is between 1900 and 2015. 
9. Year is greater than 2015.
![image](https://user-images.githubusercontent.com/123552037/231672655-573acf9c-f637-4e7b-9c18-79dfc04d8c98.png)

Programs:
P1: The function linearSearch searches for a value v in an array of integers a. If v appears in the array
a, then the function returns the first index i, such that a[i] == v; otherwise, -1 is returned.
int linearSearch(int v, int a[])
{
int i = 0; (1) 
while (i < a.length) (2)
{
if (a[i] == v) (3)
return(i); (4)
i++; (5)
}
return (-1); (6)
}


![image](https://user-images.githubusercontent.com/123552037/231545614-06562e55-97a5-44a1-870a-2cd410898439.png)
![image](https://user-images.githubusercontent.com/123552037/231673126-4fa3246d-bbc2-4659-9f15-29ec78175d1f.png)


P2:The function countItem returns the number of times a value v appears in an array of integers a.
int countItem(int v, int a[])
{
int count = 0;
for (int i = 0; i < a.length; i++)
{
if (a[i] == v) count++;
}
return (count);
}

![image](https://user-images.githubusercontent.com/123552037/231545768-aef60a63-dfd9-479f-b059-dad459d65a41.png)
![image](https://user-images.githubusercontent.com/123552037/231673374-feb3a0ac-a4e5-4394-a1f8-655c72099ba7.png)

P3: The function binarySearch searches for a value v in an ordered array of integers a. If v appears in
the array a, then the function returns an index i, such that a[i] == v; otherwise, -1 is returned.
Assumption: the elements in the array a are sorted in non-decreasing order.
int binarySearch(int v, int a[])
{
int lo,mid,hi;
lo = 0;
hi = a.length-1;
while (lo <= hi)
{
mid = (lo+hi)/2;
if (v == a[mid])
return (mid);
else if (v < a[mid])
hi = mid-1;
else
lo = mid+1;
}
return(-1);
}

![image](https://user-images.githubusercontent.com/123552037/231545913-47e1f42e-cf6a-42dc-98cd-5c8983b938ef.png)
![image](https://user-images.githubusercontent.com/123552037/231673608-ca9789bb-f154-4d23-8a80-040714b9bbed.png)

P4: The following problem has been adapted from The Art of Software Testing, by G. Myers (1979). The
function triangle takes three integer parameters that are interpreted as the lengths of the sides of a
triangle. It returns whether the triangle is equilateral (three lengths equal), isosceles (two lengths equal),
scalene (no lengths equal), or invalid (impossible lengths).
final int EQUILATERAL = 0;
final int ISOSCELES = 1;
final int SCALENE = 2;
final int INVALID = 3;
int triangle(int a, int b, int c)
{
if (a >= b+c || b >= a+c || c >= a+b)
return(INVALID);
if (a == b && b == c)
return(EQUILATERAL);
if (a == b || a == c || b == c)
return(ISOSCELES);
return(SCALENE);

}

![image](https://user-images.githubusercontent.com/123552037/231546043-22caf6b0-ce3e-4401-b9bd-406ac45ba253.png)
![image](https://user-images.githubusercontent.com/123552037/231673669-e01c19b0-dd2d-4069-8553-d60722d656e3.png)

P5: The function prefix (String s1, String s2) returns whether or not the string s1 is a prefix
of string s2 (you may assume that neither s1 nor s2 is null).
public static boolean prefix(String s1, String s2)
{
if (s1.length() > s2.length())
{
return false;
}
for (int i = 0; i < s1.length(); i++)
{
if (s1.charAt(i) != s2.charAt(i))
{
return false;
}
}
return true;
}

![image](https://user-images.githubusercontent.com/123552037/231546131-04305ac2-bd0c-44f6-88dc-3f82cb648294.png)
![image](https://user-images.githubusercontent.com/123552037/231673721-b6d89cf4-8d4f-4bd5-94d0-b7401c5f17cb.png)

P6: Consider again the triangle classification program (P4) with a slightly different specification: The program
reads floating values from the standard input. The three values A, B, and C are interpreted as
representing the lengths of the sides of a triangle. The program then prints a message to the standard output
that states whether the triangle, if it can be formed, is scalene, isosceles, equilateral, or right angled.
Determine the following for the above program:
a) Identify the equivalence classes for the system
b) Identify test cases to cover the identified equivalence classes. Also, explicitly mention which test case
would cover which equivalence class.
(Hint: you must need to be ensure that the identified set of test cases cover all identified equivalence
classes)
c) For the boundary condition A + B > C case (scalene triangle), identify test cases to verify the
boundary.
d) For the boundary condition A = C case (isosceles triangle), identify test cases to verify the boundary.
e) For the boundary condition A = B = C case (equilateral triangle), identify test cases to verify the boundary.
f) For the boundary condition A2 + B2 = C2 case (right-angle triangle), identify test cases to verify the boundary.
g) For the non-triangle case, identify test cases to explore the boundary.
h) For non-positive input, identify test points.

Ans:
a) Equivalence Classes:
Invalid inputs: When any of the input values are non-numeric or negative.
Non-triangle: When the sum of the lengths of any two sides is less than or equal to the length of the third side.
Equilateral triangle: When all sides are equal in length.
Isosceles triangle: When two sides are equal in length and the third side is different.
Scalene triangle: When all sides are different in length.
Right-angled triangle: When the sum of the squares of the lengths of the two shorter sides is equal to the square of the length of the longest side.
b) Test cases:
Invalid inputs: "a", -5, "c"
Non-triangle: 1, 2, 5
Equilateral triangle: 3, 3, 3
Isosceles triangle: 5, 7, 5
Scalene triangle: 3, 4, 5
Right-angled triangle: 3, 4, 5
c) Test cases for boundary condition A + B > C:
1, 2, 3
3, 4, 7
5, 6, 11
d) Test cases for boundary condition A = C:
1, 2, 2
4, 5, 4
6, 7, 6
e) Test cases for boundary condition A = B = C:
0.5, 0.5, 0.5
1, 1, 1
10, 10, 10
f) Test cases for boundary condition A^2 + B^2 = C^2:
3, 4, 5
5, 12, 13
7, 24, 25
g) Test cases for non-triangle:
1, 2, 3
2, 3, 5
4, 5, 9
h) Test cases for non-positive input:
0, 1, 2
-1, -2, -3

Section B:

![image](https://user-images.githubusercontent.com/123552037/231546391-cfed4001-ba1d-4d1d-a931-3e713e444bd9.png)

a. Test set for Statement Coverage:
The test set should cover every statement in the code at least once.
Test Set:
p = new Point[]{new Point(0,0), new Point(1,1)}
doGraham(p)
Explanation:
This test set contains two points, one with coordinates (0,0) and the other with coordinates (1,1). The doGraham() method is called with these two points as input. This test set will cover every statement in the code at least once.
b. Test set for Branch Coverage:
The test set should cover every possible branch in the code.
Test Set:
p = new Point[]{new Point(0,0), new Point(1,1), new Point(-1,-1)}
doGraham(p)
Explanation:
This test set contains three points, one with coordinates (0,0), one with coordinates (1,1) and one with coordinates (-1,-1). The doGraham() method is called with these three points as input. This test set will cover every possible branch in the code.


c. Test set for Basic Condition Coverage:
The test set should cover every possible condition in the code, including both true and false evaluations.
Test Set:
p = new Point[]{new Point(0,0), new Point(1,1), new Point(-1,-1)}
doGraham(p)
Explanation:
This test set contains three points, one with coordinates (0,0), one with coordinates (1,1) and one with coordinates (-1,-1). The doGraham() method is called with these three points as input. This test set will cover every possible condition in the code, including both true and false evaluations.




