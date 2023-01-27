
Part 1

StringServer

Working StringServer



String Server Code

The 2 methods in my code are handleRequest in the Handler class and a main method in the StringServer class. The main method creates a web server by
creating using the Server and inputting an instance of Handler along with the user inputted port number. The Server file calls the handleRequest method.
The handleRequest method takes in a url as a parameter. First, I have a if statement if there is an empty path and return "StringServer" if that is the case.
If the path is not empty, the else statement checks if url contains /add-message. Then the code splits the remaining part of path after ? into an array of strings.
The first string is "s" and second string in the array is the content to be added to server. I created a string variable called content and 
the second string is appended along with a new line character.
