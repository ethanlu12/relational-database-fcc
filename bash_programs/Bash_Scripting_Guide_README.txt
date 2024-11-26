# Bash Scripting Guide

This guide provides an overview of essential Bash scripting concepts, commands, and examples for efficient shell scripting.

## Basics
### Shebang
```bash
#!/bin/bash
```
The shebang specifies the interpreter to be used (in this case, Bash).

### Making a Script Executable
```bash
chmod +x filename.sh
```
This command grants executable permissions to your script, allowing you to run it as `./filename.sh`.

### Variables
#### Creating a Variable
```bash
VARIABLE_NAME=VALUE
```

#### Using a Variable
```bash
echo $VARIABLE_NAME
```

### Reading User Input
```bash
read VARIABLE_NAME
```
This command stores the user's input in `VARIABLE_NAME`.

### Printing with Newlines
```bash
echo -e "\nText with new lines\n"
```

### Accessing Script Arguments
- Print all arguments:
  ```bash
  echo $*
  ```
- Print the first argument:
  ```bash
  echo $1
  ```

## Conditional Statements
### Integer Comparison Operators
| Operator | Description             |
|----------|-------------------------|
| `-eq`    | Equal to                |
| `-ne`    | Not equal to            |
| `-lt`    | Less than               |
| `-le`    | Less than or equal to   |
| `-gt`    | Greater than            |
| `-ge`    | Greater than or equal to|

### Example:
```bash
if [[ $VARIABLE -eq 10 ]]; then
  echo "Variable equals 10"
elif [[ $VARIABLE -lt 10 ]]; then
  echo "Variable is less than 10"
else
  echo "Variable is greater than 10"
fi
```

### Pattern Matching
```bash
[[ "hello world" =~ ^h ]]; echo $?
```
This checks if the string "hello world" matches the pattern starting with `h`.

## Math Operations
- Perform calculations without output:
  ```bash
  (( OPERATION ))
  ```
- Store calculation results:
  ```bash
  RESULT=$(( OPERATION ))
  ```
Example:
```bash
NUMBER=$(( RANDOM % 75 + 1 ))
```
This generates a random number between 1 and 75.

## Arrays
### Creating an Array
```bash
ARR=("a" "b" "c")
```

### Accessing Array Elements
- Print the second element:
  ```bash
  echo ${ARR[1]}
  ```
- Print all elements:
  ```bash
  echo ${ARR[@]}
  ```

## Functions
### Defining a Function
```bash
FUNCTION_NAME() {
  STATEMENTS
}
```

### Calling a Function
```bash
FUNCTION_NAME
```

Example:
```bash
say_hello() {
  echo "Hello, $1!"
}
say_hello "World"
```

## Loops
### Until Loop
```bash
until [[ CONDITION ]]; do
  STATEMENTS
done
```

Example:
```bash
COUNT=1
until [[ $COUNT -gt 5 ]]; do
  echo "Count is $COUNT"
  ((COUNT++))
done
```

## Viewing and Declaring Variables
- View all shell variables:
  ```bash
  declare -p
  ```
- Declare a variable:
  ```bash
  declare VARIABLE_NAME=VALUE
  ```

---

This guide covers the essentials to get you started with Bash scripting. Refer to the examples provided and expand upon them for your use cases.
