# Lab-7_202001147

Name: Parth Patel

ID: 202001147

Lab: 07 - Black-box and white-box testing

# Section A

The possible test cases for the program to calculate previous Date are as follows

1. Equivalence Partitioning 

Input Data | Expected Outcome
:--------: | ---------------
Valid day, Month, and Year | Previous Date
Invalid day < 1 or > 31 | Error Message
Invalid month < 1 or > 12 | Error Message
Invalid year < 1900 or > 2015 | Error Message

2. Boundary Value Analysis (DD-MM-YYYY) 

Input Data | Expected Outcome
---------- | ---------------
01/01/1990 | INVALID
28/2/1990 | 27/2/1900
29/02/2001 | INVALID
29/02/2012 | 28/02/2012
1/5/2000 | 30/4/2000
31/06/2010 | INVALID
31/12/2015 | 30/12/2015

I made 5 distinct JAVA files, file1.java, file2.java, file3.java, file4.java, and file5.java, to test the scripts. The matching function code to be tested is contained in each file.
> Code for doing linear search on an array of integers in file1.java is provided to retrieve the index of a certain number. It returns -1 if fails to locate.

Test Cases for *linearSearch(int x, int[] arr)*


import static org.junit.jupiter.api.Assertions.*;
class Test1 {
  @Test
  void returnIndex1() {
    int[] arr = {8, 2, -7, -13, 2, 5, -3};
    int expected = 5;
    int x = 5;
    assertEquals(file1.linearSearch(x, arr), expected);
  }
  @Test
  void returnIndex2() {
    int[] arr = {8, 2, -7, -13, 2, 5, -3};
    int expected = 1;
    int x = 2;
    assertEquals(file1.linearSearch(x, arr), expected);
  }
  @Test
  void returnInvalid1() {
    int[] arr = {8, 2, -7, -13, 2, 5, -3};
    int expected = -1;
    int x = 4;
    assertEquals(file1.linearSearch(x, arr), expected);
  }
  @Test
  void returnInvalid2() {
    int[] arr = {8, 2, -7, -13, 2, 5, -3};
    int expected = -1;
    int x = -6;
    assertEquals(file1.linearSearch(x, arr), expected);
  }
}


For the  given inputs, 

TesterAction and Input Data  | Expected Outcome | Test Case Type
---------------------------  | :--------------: | --------------
arr=[8,2,-7,-13,2,5,-3], x=5 | 5 | Equivalence Partitioning
arr=[8,2,-7,-13,2,5,-3], x=2 | 1 | Equivalence Partitioning
arr=[8,2,-7,-13,2,5,-3], x=4 | -1 | Boundary Value Analysis
arr=[8,2,-7,-13,2,5,-3], x=-6 | -1 | Boundary Value Analysis

> file2.java counts occurrence of a particular value in an array of integers.

Test Cases for *CountElement(int x, int[] arr)*


import static org.junit.jupiter.api.Assertions.*;

class Test2 {
	@Test
	void present1() {
		int[] arr = {5,5,2,-3,6,7,-2,5,2,6};
		int x = 5;
		int count = 3;
		assertEquals(file2.countElement(x, arr), count);
	}
	@Test
	void absent1() {
		int[] arr = {5,5,2,-3,6,7,-2,5,2,6};
		int x = 1;
		int count = 0;
		assertEquals(file2.countElement(x, arr), count);
	}
	@Test
	void present2() {
		int[] arr = {5,5,2,-3,6,7,-2,5,2,6};
		int x = 7;
		int count = 1;
		assertEquals(file2.countElement(x, arr), count);
	}
	@Test
	void absent2() {
		int[] arr = {5,5,2,-3,6,7,-2,5,2,6};
		int x = -4;
		int count = 0;
		assertEquals(file2.countElement(x, arr), count);
	}
}


For given inputs,

TesterAction and Input Data  | Expected Outcome | Test Case Type
---------------------------  | :--------------: | --------------
arr=[5,5,2,-3,6,7,-2,5,2,6], x=5 | 3 | Equivalence Partitioning
arr=[5,5,2,-3,6,7,-2,5,2,6], x=1 | 0 | Boundary Value Analysis
arr=[5,5,2,-3,6,7,-2,5,2,6], x=7 | 1 | Boundary Value Analysis
arr=[5,5,2,-3,6,7,-2,5,2,6], x=-4 | 0 | Boundary Value Analysis

>file3.java performs binary search on a sorted array of integers to find a specific value. It returns -1, if the value is not found.

Test Cases for *binarySearch(int x, int[] arr)*


import static org.junit.jupiter.api.Assertions.*;

class Test3 {
	@Test
	void findElement1() {
		int[] arr = {0,1,2,3,4,5,6,7,8,9};
    int x = 6;
    int expected = 6;
		assertEquals(file3.binarySearch(x, arr), expected);
	}
	@Test
	void findElement2() {
		int[] arr = {0,2,3,5,8,13};
    int x = 13;
    int expected = 5;
		assertEquals(file3.binarySearch(x, arr), expected);
	}
	@Test
	void findElement3() {
		int[] arr = {0,2,3,5,8,13};
    int x = 0;
    int expected = 0;
		assertEquals(file3.binarySearch(x, arr), expected);
	}
	@Test
	void absentElement1() {
		int[] arr = {0,2,3,5,7,11};
    int x = 6;
    int expected = -1;
		assertEquals(file3.binarySearch(x, arr), expected);
	}
	@Test
	void absentElement2() {
		int[] arr = {};
    int x = 2;
    int expected = -1;
		assertEquals(file3.binarySearch(x, arr), expected);
	}
}


For given inputs,

TesterAction and Input Data  | Expected Outcome | Test Case Type
---------------------------  | :--------------: | --------------
arr=[0,1,2,3,4,5,6,7,8,9], x=6 | 6 | Equivalence Partitioning
arr=[0,2,3,5,8,13], x=13 | 5 | Equivalence Partitioning
arr=[0,2,3,5,8,13], x=0 | 0 | Boundary Value Analysis
arr=[0,2,3,5,7,11], x=6 | -1 | Boundary Value Analysis
arr=[], x=2 | -1 | Boundary Value Analysis

> file4.java checks if given measurements are sides of a SCALENE (2), ISOSCELES (1), or an EQUILATERAL (0) triangle. Returns INVALID (3) if given sides cannot form any triangle.

Test Cases for *triangle(int a, int b, int c)*


import static org.junit.jupiter.api.Assertions.*;

class Test4 {
	@Test
	void invalid1() {
		int a = 0, b = 0, c = 0;
		int expected = file4.INVALID;
		assertEquals(file4.triangle(a, b, c), expected);
	}
	@Test
	void invalid2() {
		int a = 0, b = 4, c = 0;
		int expected = file4.INVALID;
		assertEquals(file4.triangle(a, b, c), expected);
	}
	@Test
	void invalid3() {
		int a = 9, b = 8, c = 0;
		int expected = file4.INVALID;
		assertEquals(file4.triangle(a, b, c), expected);
	}
	@Test
	void invalid4() {
		int a = 9, b = 8, c = 200;
		int expected = file4.INVALID;
		assertEquals(file4.triangle(a, b, c), expected);
	}
	@Test
	void invalid5() {
		int a = -7, b = -7, c = -7;
		int expected = file4.INVALID;
		assertEquals(file4.triangle(a, b, c), expected);
	}
	@Test
	void equilateral1() {
		int a = 5, b = 5, c = 5;
		int expected = file4.EQUILATERAL;
		assertEquals(file4.triangle(a, b, c), expected);
	}
	@Test
	void equilateral2() {
		int a = 50, b = 50, c = 50;
		int expected = file4.EQUILATERAL;
		assertEquals(file4.triangle(a, b, c), expected);
	}
	@Test
	void isosceles1() {
		int a = 10, b = 10, c = 12;
		int expected = file4.ISOSCELES;
		assertEquals(file4.triangle(a, b, c), expected);
	}
	@Test
	void isosceles2() {
		int a = 12, b = 10, c = 10;
		int expected = file4.ISOSCELES;;
		assertEquals(file4.triangle(a, b, c), expected);
	}
	@Test
	void isosceles3() {
		int a = 50, b = 25, c = 50;
		int expected = file4.ISOSCELES;;
		assertEquals(file4.triangle(a, b, c), expected);
	}
	@Test
	void scalene1() {
		int a = 5, b = 6, c = 10;
		int expected = file4.SCALENE;
		assertEquals(file4.triangle(a, b, c), expected);
	}
}

For given inputs,

TesterAction and Input Data  | Expected Outcome | Test Case Type
---------------------------  | :--------------: | --------------
a = 0, b = 0, c = 0 | INVALID | Boundary Condition
a = 0, b = 4, c = 0 | INVALID | Boundary Condition
a = 9, b = 8, c = 0 | INVALID | Boundary Condition
a = 9, b = 8, c = 200 | INVALID | Equivalance Partitioning
a = -7, b = -7, c = -7 | INVALID | Boundary Condition
a = 5, b = 5, c = 5 | EQUILATERAL | Equivalance Partitioning
a = 50, b = 50, c = 50 | EQUILATERAL | Equivalance Partitioning
a = 10, b = 10, c = 12 | ISOSCELES | Equivalance Partitioning
a = 12, b = 10, c = 10 | ISOSCELES | Equivalance Partitioning
a = 50, b = 25, c = 50 | ISOSCELES | Equivalance Partitioning
a = 5, b = 6, c = 10 | SCALENE | Boundary Condition

> file5.java checks if string s1 is a prefix to string s2 or not.

Test Cases for *prefix(String s1, String s2)*


import static org.junit.jupiter.api.Assertions.*;

class Test5 {
	@Test
	void isPrefix1() {
		assertTrue( file5.prefix("", "") );
	}
	@Test
	void isPrefix2() {
		assertTrue( file5.prefix("app", "apple") );
	}
	@Test
	void isPrefix3() {
		assertTrue( file5.prefix("apple", "apple") );
	}
	@Test
	void isPrefix4() {
		assertTrue( file5.prefix("", "apple") );
	}
	@Test
	void notPrefix2() {
		assertFalse( file5.prefix("app le", "apple"));
	}
	@Test
	void notPrefix3() {
		assertFalse( file5.prefix(" app", "apple"));
	}
	@Test
	void notPrefix1() {
		assertFalse( file5.prefix("apple", "app"));
	}
}

For given inputs,

TesterAction and Input Data  | Expected Outcome | Test Case Type
---------------------------  | :--------------: | --------------
s1="", s2="" | true | Boundary Condition
s1="app", s2="apple" | true | Equivalence Partitioning
s1="apple", s2="apple" | true | Boundary Condition
s1="", s2="apple" | true | Boundary Condition
s1="app le", s2="apple" | false | Boundary Condition
s1=" app", s2="apple" | false | Boundary Condition
s1="apple", s2="app" | false | Equivalence Partitioning

> file6 assumes the problem domain of file4 with A, B, and C as floating values instead of integers

## A. Equivalence classes for the system

possible equivalence classes and their corresponding conditions:

Equivalence Class | Neccesary Condition
---------- | ---------------
Equilateral Triangle | $A == B$ and $B == C$
Invalid Triangle | $A > B+C$ or $B > A+C$ or $C > A+B$
Isoceles Triangle | $A == B$ or $B == C$ or $A == C$
Right-angle Triangle | $A^2 + B^2 = C^2$ or $A^2 = B^2 + C^2$ or $B^2 + A^2 = C^2$
Scalene Triangle | $A!=B$ and $B!=C$ and $C!=A$

## B. Test Cases for Equivalence Classes

list of test cases each belonging to one of the defined Equivalence class:

Test Case | Condition | Expected Outcome
:---: | ----- | ----- 
1 | A = 5, B = 5, C = 5 | Equilateral Triangle
2 | A = 1, B = 1, C = 3	| Invalid Triangle
3 | A = 2, B = 2, C = 3	| Isosceles Triangle
4 | A = 3, B = 4, C = 5	| Right-angle Triangle
5 | A = 4, B = 4, C = 7	| Scalene Triangle

## C. Boundary Condition $A + B > C$ (scalene triangle)
list of possible edge cases looking like scalene triangle but aren't

Test Case | Condition | Expected Outcome
:---: | ----- | ----- 
1 | A = 1, B = 2, C = 2.9 | Scalene Triangle
2 | A = 1, B = 2, C = 3	| Invalid Triangle
3 | A = 1, B = 1, C = 2	| Invalid Triangle
4 | A = 2, B = 3, C = 5	| Invalid Triangle
5 | A = 0.1, B = 0.1, C = 0.3 | Invalid Triangle

## D. Boundary Condition $A = C$ (isosceles triangle)
list of possible edge cases looking like isosceles triangle but aren't

Test Case | Condition | Expected Outcome
:---: | ----- | ----- 
1 | A = 0.15, B = 0.2, C = 0.15 | Isosceles Triangle
2 | A = 0, B = 2, C = 0	| Invalid Triangle
3 | A = 0.1, B = 0.3, C = 0.1	| Invalid Triangle
4 | A = 1, B = 3, C = 1	| Invalid Triangle
5 | A = -4, B = 3, C = -4 | Invalid Triangle

## E. Boundary Condition $A = B = C$ (equilateral triangle)

list of possible edge cases looking like isosceles triangle but aren't

Test Case | Condition | Expected Outcome
:---: | ----- | ----- 
1 | A = 0.5, B = 0.5, C = 0.5 | Equilateral Triangle
2 | A = 4, B = 4, C = 4 | Equilateral Triangle
3 | A = 0, B = 0, C = 0	| Invalid Triangle
4 | A = -3, B = -3, C = -3 | Invalid Triangle

## F. Boundary Condition $A^2 + B^2 = C^2$ (right-angle triangle)

list of possible corner cases looking like right-angle triangle but aren't

Test Case | Condition | Expected Outcome
:---: | ----- | ----- 
1 | A = 1, B = 1.414, C = 1.73 | Right Angled Triangle
2 | A = 6, B = 8, C = 10 | Right Angled Triangle
3 | A = -1, B = 1.414, C = -1.73 | Invalid Triangle
4 | A = 6, B = -8, C = 10 | Invalid Triangle

## G. Non-triangle Case

list of possible Invalid Triangle cases

Test Case | Condition | Expected Outcome
:---: | ----- | ----- 
1 | A = 0, B = 0, C = 0 | Invalid Triangle
2 | A = 1, B = 1.414, C = -9.73 | Invalid Triangle
3 | A = 3, B = 4, C = 8 | Invalid Triangle
4 | A = -1, B = -1.414, C = 1.73 | Invalid Triangle
5 | A = -4, B = -3, C = 5 | Invalid Triangle
6 | A = 111, B = 1.414, C = 9.73 | Invalid Triangle
7 | A = 1, B = 60, C = 9.73 | Invalid Triangle

H. Non-positive Input

list of possible Invalid Triangle cases

Test Case	Condition	Expected Outcome
1	a=-1, b=2, c=3	Invalid Triangle
2	a=-4, b=-5, c=-7	Invalid Triangle
3	a=1, b=-5, c=10	Invalid Triangle

# Section B

## 1. Control flow graph

![1 drawio (2)](https://user-images.githubusercontent.com/83646997/231789294-ee81c29f-61ee-4642-99db-377ed46012d6.png)


## 2. Criteria specific test case for flow graph

### a. Statement Coverage

Test Case | Input | Expected Output
:---: | ----- | ----- 
1 | p=[] | Empty Vector
2 | p=[(1,1)] | Vector with Single Point
3 | p=[(1,1),(2,2),(3,3)] | Vector with 3 Points

### b. Branch Coverage

Test Case | Input | Expected Output
:---: | ----- | ----- 
1 | p=[] | Empty Vector
2 | p=[(1,1),(2,2)] | Vector with 2 points
3 | p=[(1,1),(2,2),(3,1),(4,3)] | Vector with 4 Points
4 | p=[(1,2),(3,1),(2,1)] | Vector with 3 points in different order


### c. Basic Condition Coverage

Test Case | Input | Expected Output
:----: | ---- | ----
1 | p=[] | Empty Vector
2 | p=[(1,1),(2,2)] | Vector with 2 points
3 | p=[(1,1),(1,1),(1,1)] | vector with identical points
4 | p=[(1,1),(2,2),(1,1)] | vector with two identical points
5 | p=[(1,1),(2,2),(3,1),(4,3)] | vector with 4 points
6 | p=[(1,2),(3,1),(2,1)] | Vector with 3 indentical points
