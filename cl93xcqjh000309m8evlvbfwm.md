# How to Bash Script Like a Pro


### Introduction

The shell is a UNIX program that provides an interface to the operating system. It allows you to type commands to control the system. The shell is not just a way to run other programs; it is a programming language in its own right.

There are many different shells available, but the most popular is bash. This tutorial will teach you the basics of bash programming.

### The Basics

In order to run a bash program, you need to type the commands into a text editor and save them to a file. The file must have the ".sh" extension. For example, you could save the following program to a file called "hello.sh":

```
#!/bin/bash

echo "Hello, world!"
```

You can then run the program by typing "./hello.sh" at the command prompt.

The first line of the program, `#!/bin/bash`, is called a shebang. It tells the system which interpreter to use to run the program. In this case, we are using the bash shell.

The second line of the program is a simple command that prints the text "Hello, world!" to the screen.

### Variables

You can store data in variables for use in your program. For example, you could store your name in a variable and then print it to the screen:

```
#!/bin/bash

name="Jared"
echo "Hello, $name!"
```

Here we have defined a variable called `name` and assigned it the value "Jared". We then used the variable in an echo statement to print out a greeting.

Note that we have used the dollar sign ($) to denote that we are using a variable. This is necessary in order to get the value of the variable, rather than the literal text "$name".

You can also define variables without assigning them a value:

```
#!/bin/bash

name
echo "Hello, $name!"
```

In this case, the variable "name" will be empty. Running the program will print out "Hello, !"

You can also use the read command to get input from the user and store it in a variable:

```
#!/bin/bash
read -p "Enter your name: " name
echo "Hello, $name!"
```

The read command takes input from the user and stores it in the variable "name". The -p option tells read to prompt the user with the given text.

### Conditionals

You can use conditionals to control the flow of your program. For example, you could ask the user for their age and then print out a message depending on whether they are 18 or not:

```
#!/bin/bash
read -p "Enter your age: " age
if [ "$age" -eq 18 ]
then
  echo "You are old enough to buy a beer."
else
  echo "You are not old enough to buy a beer."
fi
```

Here we are using the if statement to execute the code in the "then" block if the age is equal to 18. Otherwise, the code in the "else" block will be executed.

The -eq operator is used to test for equality. There are many other operators that can be used for different purposes, such as -gt for greater than and -lt for less than.

You can also use the && operator to combine multiple conditions:

```
#!/bin/bash
read -p "Enter your age: " age
read -p "Enter your name: " name

if [ "$age" -gt 18 ] && [ "$name" = "Jared" ]
then
  echo "You are old enough to buy a beer."
else
  echo "You are not old enough to buy a beer."
fi
```

In this example, the code in the "then" block will only be executed if the age is greater than 18 AND the name is equal to "John".

Alternatively, you could use the || operator to execute the code in the "then" block if either condition is true:

```
#!/bin/bash
read -p "Enter your age: " age
read -p "Enter your name: " name

if [ "$age" -gt 18 ] || [ "$name" = "Jared" ]
then
  echo "You are old enough to buy a beer."
else
  echo "You are not old enough to buy a beer."
fi
```

In this example, the code in the "then" block will be executed if the age is greater than 18 OR the name is equal to "Jared".

You can also use the ! operator to invert a condition:

```
#!/bin/bash
read -p "Enter your age: " age

if [ ! "$age" -eq 18 ]
then
  echo "You are not 18."
else
  echo "You are 18."
fi
```

In this example, the code in the "then" block will be executed if the age is not equal to 18.

### Loops

Loops allow you to repeat a block of code multiple times. For example, you could use a loop to print out the numbers from 1 to 10:

```
#!/bin/bash
for i in {1..10}
do
  echo "$i"
done
```

The for loop will execute the code in the "do" block for each value in the given sequence. In this case, the sequence is the numbers 1 to 10.

You can also use a while loop to execute a block of code until a condition is no longer true:

```
#!/bin/bash

i=0

while [ "$i" -lt 10 ]
do
  echo "$i"
  i=$((i+1))
done
```

The code in the "do" block will be executed until the condition in the "while" statement is no longer true. In this case, the condition is that the value of "i" is less than 10.

The final line of the program increments the value of "i" by 1 each time the loop is executed. This ensures that the condition will eventually become false and the loop will terminate.

### Functions

Functions allow you to group together a block of code to be executed when necessary. For example, you could define a function to print out a greeting:

```
#!/bin/bash

function greeting() {
  echo "Hello, world!"
}

greeting
```

The "greeting" function is defined in the "do" block and can be executed by typing "greeting" at the command prompt.

You can also pass arguments to a function:

```
#!/bin/bash

function greeting() {
  echo "Hello, $1!"
}

greeting "Jared"
```

Here we are passing the argument "Jared" to the "greeting" function. The function then prints out "Hello, Jared!".

You can also return values from a function:

```
#!/bin/bash

function greeting() {
  echo "Hello, world!"
  return 0
}

greeting
```

The "greeting" function prints out a greeting and returns the value 0. This value can be used to indicate that the function was executed successfully.

### Conclusion

This tutorial has taught you the basics of bash programming. You should now be able to write simple programs to control the UNIX operating system.