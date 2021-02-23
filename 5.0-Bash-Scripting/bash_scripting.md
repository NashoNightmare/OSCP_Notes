
## 5.0 Bash Scripting

**Shebang** : `#!/bin/bash`, `#!/bin/bash -x` : `-x` flag for additional debug output -  This is what makes this a “Bash script” as opposed to another type of shell script, like a “C Shell script”.

**Initializing Variables** : `variable_name="Variable_Content"` 

**Referring Variables** : `echo "Your variable is $variable_name"` , `echo $variable_name` , `variable_name2="Variable 1 $variable_name"`

**Command substituition(Assign the output of a program to a variable)** : `variable_name=$(command)`

**Arguments** : `echo "The first two arguments are $1 and $2"`- The first 9 arguments to the Bash script can be $1 to $9.
![alt text](https://github.com/NashoNightmare/OSCP-Notes/blob/master/special_bash_variables.png)

**Reading User Input** : `read variable_name` , To refer the user input `echo "The user input is $variable_name"`

**Conditional Statements** :
	
	If [<some_test>]
	then
		<perform_an_action>
	elif [<some_test>]
	then
		<perform_different_action>
	else
		<perform_yet_another_different_action>
	fi

![alt txt](https://github.com/NashoNightmare/OSCP-Notes/blob/master/common_test_command_operators.png)

**Boolean Logic Operators**
1. Using Boolean Operators in non-conditional statements : 
	
	- `command1 && command2` - Command 2 executes if command 1 succeeds(Exit Status 0).
	- `command1 || command2` - Command 2 executes if command 1 fails(Any exit Status except 0).

2. Using Boolean Operators in conditional statements : The same functionality of Boolean operators on C program conditional statements occurs herea as well.

**Loops**
1. For loop

		_______________________________________
		for <var_name> in <list>
		do 
			<action_to_perform>
		done
		_______________________________________
		for <var_name> in $(seq 1 10)
		do
			<action_to_perform>
		done
		_______________________________________
		for <var_name> in {1..10}
		do 
			<action_to_perform>
		done
		_______________________________________

2. While loop			

		_______________________________________
		counter=1
		while [	$counter -lt 10 ]
		do
			<action_to_perform>
		done
		_______________________________________
		while [ $counter -le 10 ]
		do
			<action_to_perform>
		done
		_______________________________________
		while [ $counter -gt 10 ]
		do
			<action_to_perform>
		done
		_______________________________________
		while [ $counter -ge 10 ]
		do
			<action_to_perform>
		done
		_______________________________________

**Functions**

		_______________________________________
		function_name(){
		<commands>
		}
		_______________________________________
To use the function : `function_name

We can pass the arguments to the function by using same procedure we done for the bash programs. Literally the function in a bash program is a program-in-a-program

Example : 

		function function_one {
			echo "Hello $1"
		}

		function_one 20

To declare local variables : Use `local` keyword to define a local variable.
		
		_______________________________________
		function_name(){
			local_variable = "content"
		}
		_______________________________________

