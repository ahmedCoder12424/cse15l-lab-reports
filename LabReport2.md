#1 CSE15L Lab Report 2
__Part 1__

__StringServer___

__Working StringServer__

![Image](StringSrvr1.png)
![Image](StringSrvr2.png)
![Image](StringSrvr3.png)

__String Server Code__

![Image](StringServerCode1.png)

![Image](StringServerCode2.png)

The 2 methods in my code are `handleReques()` in the Handler class and a main method in the StringServer class. The main method creates a web server by
creating using the `Server.java` and inputting an instance of Handler along with the user inputted port number. The Server file calls the handleRequest method.
The handleRequest method takes in a url as a parameter. First, I have a if statement if there is an empty path and return "StringServer" if that is the case.
If the path is not empty, the else statement checks if url contains `/add-message`. Then the code splits the remaining part of path after `?` into an array of strings.
The first string is `"s"` and second string in the array is the content to be added to server. I created a string variable called content and 
the second string is appended along with a new line character.


__Part 2__


__reverseInPlace()__

1) __Failure Inducing Input__ - {1,2,3}

expected output: {3,2,1}  actual output: {3,2,3}
```
  @Test
  public void testReverseInPlace2() {
    int[] input1 = { 1,2,3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3,2,1 }, input1);
	}

```

2) __Successful Input__  - {1,1,1}

expected output: {1,1,1}  actual output: {1,1,1}

```
@Test 
public void testReverseInPlace() {
    int[] input1 = { 1,1,1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1,1,1 }, input1);
	}
```


3) __Symptom__ - Incorrect Output, output is not reversed version of input


4) __Bug__ - The loop should run only length/2 times and should be assigning `arr[arr.length-i-1]` to the original value of `a[i]`.

Code before bug fixed
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }

```


Code after bug fixed 
```
 static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp =arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }

```
__Part 3__

In week 2, I learned how URL paths are parsed by webservers to change output on webpage. In week 3, I learned to distinguish the particular terminology
around programming errors such as bugs, symptoms, failure inducing inputs.




