
# Shell Command

## Chapter 1: Introduction to Linux Commands

### 1.1 Structure of Shell Command

The general structure of a shell command is as follows:

```bash
command params -options
```

- **command**: The name of the command to be executed.
- **params**: Optional parameters (arguments) that provide specific information to the command.
- **-options**: Optional flags that modify the command's behavior.

---

### 1.2 Navigating Directories

- **`pwd`**: Prints the current working directory.

```bash
pwd
```

Example:  
`pwd` will display the current directory path, such as `/home/user`.

- **`cd`**: Changes the current working directory.

```bash
cd [directory]
```

Examples:  
- `cd Documents`: Changes the directory to the `Documents` directory within the current directory.  
- **Relative Path**: `cd ..` moves to the parent directory.  
- **Absolute Path**: `cd /home/user/Documents` moves to the `Documents` directory within `/home/user`.

---

### 1.3 File and Directory Management

- **`ls`**: Lists files and directories.

```bash
ls [options] [files]
```

Examples:  
- `ls`: Lists all files and directories in the current directory.  
- `ls -l`: Displays a detailed listing, including file permissions, size, and last modified date.  
- `ls -a`: Lists all files, including hidden files (starting with `.`).

- **`mkdir`**: Creates a new directory.

```bash
mkdir [directory]
```

Example:  
`mkdir new_directory` creates a new directory called `new_directory`.

- **`rmdir`**: Removes an empty directory.

```bash
rmdir [directory]
```

Example:  
`rmdir new_directory` removes the `new_directory`.

- **`touch`**: Creates an empty file or updates a file's timestamp.

```bash
touch [file]
```

Example:  
`touch new_file.txt` creates a file called `new_file.txt` in the current directory.

- **`rm`**: Removes files.

```bash
rm [options] [files]
```

Examples:  
- `rm file.txt`: Deletes the file `file.txt`.  
- `rm -r directory`: Recursively removes the directory and all its contents.  
- `rm -i file.txt`: Prompts before deleting `file.txt` (interactive mode).

- **`cp`**: Copies files or directories.

```bash
cp [options] [source] [destination]
```

Examples:  
- `cp file.txt new_file.txt`: Creates a copy of `file.txt` named `new_file.txt`.  
- `cp -r directory new_directory`: Creates a copy of the directory and all its contents into a new directory `new_directory`.

- **`mv`**: Moves or renames files or directories.

```bash
mv [options] [source] [destination]
```

Examples:  
- `mv file.txt new_file.txt`: Renames the file `file.txt` to `new_file.txt`.  
- `mv file.txt new_directory`: Moves `file.txt` into the `new_directory`.

---

### 1.4 File Content Manipulation

- **`cat`**: Concatenates and displays files.

```bash
cat [options] [file]
```

Example:  
`cat file.txt` displays the content of `file.txt` to the terminal.

- **`echo`**: Prints text to the terminal.

```bash
echo [text]
```

Example:  
`echo "Hello, world!"` prints the text `"Hello, world!"` to the terminal.

- **`nano`**: A simple text editor for creating and editing files.

```bash
nano [file]
```

Example:  
`nano new_file.txt` opens a new file named `new_file.txt` in the nano editor.

---

### 1.5 File Searching and Display

- **`find`**: Searches for files based on specified criteria.

```bash
find [path] [options]
```

Example:  
`find . -name '*.txt'`: Finds all files ending in `.txt` in the current directory and its subdirectories.

- **`less`**: Displays file contents one screen at a time.

```bash
less [file]
```

Example:  
`less file.txt` opens `file.txt` for viewing, allowing you to scroll through the content.

- **`head`**: Displays the first few lines of a file.

```bash
head [options] [file]
```

Example:  
`head -n 10 file.txt` shows the first 10 lines of `file.txt`.

- **`tail`**: Displays the last few lines of a file.

```bash
tail [options] [file]
```

Example:  
`tail -n 10 file.txt` shows the last 10 lines of `file.txt`.

---

### 1.6 Text Searching

- **`grep`**: Searches for specific patterns within files.

```bash
grep [options] [pattern] [file]
```

Example:  
`grep "search_term" file.txt` searches for the term `"search_term"` in `file.txt` and displays matching lines.

---

### 1.7 File Permissions

- **`chmod`**: Changes the file mode (permissions).

```bash
chmod [options] [mode] [file]
```

Example:  
`chmod 755 script.sh` sets the permissions of `script.sh` to read, write, and execute for the owner, and read and execute for the group and others.

# Chapter 2: Shell Scripting Fundamentals

## 2.1 Shell Functions

**Definition**: A shell function is a block of code that performs a specific task.

**Syntax**:
```bash
function function_name {
  # Code to be executed
}
```

**Example**:
```bash
function greet {
  echo "Hello, $1!"
}

greet "World"
```

**Explanation**:  
The `greet` function takes one argument (`$1`) and prints a greeting message.  
When the `greet` function is called with the argument `"World"`, it prints `"Hello, World!"`.

---

## 2.2 Running Shell Scripts in Google Colab

**Single Line Script Execution**:  
- **Syntax**: `! command`  
- **Example**: `! echo "Hello from shell"`  
- **Explanation**: The `!` prefix tells Colab to execute the following command in the shell.

**Multi-line Script Execution**:  
- **Syntax**: Create a code cell and use the `%%bash` magic command.  
- **Example**:
```bash
%%bash
echo "This is a multi-line shell script"
ls -l
```
**Explanation**:  
The `%%bash` magic command tells Colab to execute the code in the cell as a shell script.

---

## 2.3 Shell Variables

**Definition**: Shell variables are used to store data within a shell script.  
- **Syntax**: `variable_name=value`  
- **Example**:
```bash
name="John Doe"
echo "My name is $name"
```
**Explanation**:  
The variable `name` is assigned the value `"John Doe"`.  
The `$` symbol is used to access the value stored in the variable.

---

## 2.4 Shell Metacharacters

### `>`: Redirects standard output to a file, overwriting the file if it exists.

**Example**:  
```bash
ls -l > file_list.txt
```
**Explanation**:  
The output of the `ls -l` command is redirected to the file `file_list.txt`.  
Any existing content in `file_list.txt` will be overwritten.

### `>>`: Appends standard output to a file.

**Example**:  
```bash
echo "New line" >> file_list.txt
```
**Explanation**:  
The text `"New line"` is appended to the end of the file `file_list.txt`.

### `<`: Redirects standard input from a file.

**Example**:  
```bash
sort < data.txt
```
**Explanation**:  
The `sort` command reads its input from the file `data.txt`.

### `<<`: Here document, allows multi-line input redirection.

**Example**:
```bash
cat << EOF
This is a multi-line
input.
EOF
```
**Explanation**:  
The `cat` command reads the input between the `EOF` delimiters as a multi-line string.

### `2>`: Redirects standard error output to a file.

**Example**:  
```bash
command 2> error.log
```
**Explanation**:  
Any error messages generated by the command are redirected to the file `error.log`.

---

## 2.5 The Pipeline (`|`)

**Definition**: The pipe operator (`|`) passes the output of one command as input to another command.  
**Example**:  
```bash
ls -l | grep "txt"
```
**Explanation**:  
The output of the `ls -l` command (listing of files and directories) is piped to the `grep` command, which searches for lines containing `"txt"`.

---

## 2.6 The Dollar Sign (`$`)

**Definition**: The dollar sign is used to reference variables and command substitution in shell scripts.  
**Example**:
```bash
current_date=$(date)
echo "Today's date is $current_date"
```
**Explanation**:  
The `$(date)` command substitution captures the output of the `date` command and assigns it to the variable `current_date`.  
The `echo` command then prints the current date.

---

## 2.7 Quoting

**Definition**: Quoting is used to prevent the shell from interpreting special characters.  
**Types of Quoting**:  
- **Single Quotes (`' '`)**: Preserve the literal value of each character within the quotes.  
- **Double Quotes (`" "`)**: Allow variable expansion and command substitution.

**Example**:
```bash
echo 'This is a single-quoted string'
echo "This is a double-quoted string with a variable: $name"
```
**Explanation**:  
The first `echo` command prints the string literally.  
The second `echo` command expands the variable `name` within the double quotes.

---

## 2.8 Parameter Variables

**Definition**: Parameter variables are used to access the positional parameters passed to a script or function.  
**Examples**:
- `$1`, `$2`, `$3`, ...: Represents the first, second, third, etc., arguments.  
- `$*`: Represents all positional parameters as a single word.  
- `$@`: Represents all positional parameters as separate words.

**Example**:
```bash
echo "First argument: $1"
echo "All arguments: $*"
echo "All arguments (separate): $@"
```
**Explanation**:  
When the script is executed with arguments, `$1` will display the first argument, `$*` will display all arguments as a single string, and `$@` will display each argument separately.

---

## 2.9 Some Fundemental Problem Solutions

### Get, Process, and Print Data Entered by User:
```bash
read -p "Enter your name: " user_name
echo "Hello, $user_name!"
```
**Explanation**:  
The `read` command captures user input and stores it in the variable `user_name`, which is then printed.

### Sort Data:
```bash
echo -e "banana
apple
cherry" | sort
```
**Explanation**:  
The `echo` command outputs a list of fruits, which is then sorted alphabetically by the `sort` command.

### Count Words:
```bash
echo "apple banana cherry" | wc -w
```
**Explanation**:  
The `wc -w` command counts the number of words in the input string.

### Append Data at the End:
```bash
echo "New entry" >> data.txt
```
**Explanation**:  
The `>>` operator appends the string `"New entry"` to the end of the file `data.txt`.

# Chapter 3: Shell Scripting Control Structures

## 3.1 Conditional Structures

**Definition**: Conditional structures allow you to execute different code blocks based on specific conditions.

### 3.1.1 if Statement

**Syntax**:
```bash
if [ condition ]; then
  # Code to be executed if condition is true
fi
```

**Example**:
```bash
num=10
if [ $num -gt 5 ]; then
  echo "Number is greater than 5"
fi
```

**Explanation**:  
- The if statement checks if the variable num is greater than 5.
- If the condition is true, the message "Number is greater than 5" is printed.

### 3.1.2 if-else Statement

**Syntax**:
```bash
if [ condition ]; then
  # Code to be executed if condition is true
else
  # Code to be executed if condition is false
fi
```

**Example**:
```bash
num=3
if [ $num -gt 5 ]; then
  echo "Number is greater than 5"
else
  echo "Number is not greater than 5"
fi
```

**Explanation**:  
- The if statement checks if the variable num is greater than 5.
- If the condition is true, prints "Number is greater than 5".
- If the condition is false, prints "Number is not greater than 5".

### 3.1.3 if-elif-else Statement

**Syntax**:
```bash
if [ condition1 ]; then
  # Code to be executed if condition1 is true
elif [ condition2 ]; then
  # Code to be executed if condition2 is true
else
  # Code to be executed if all conditions are false
fi
```

**Example**:
```bash
num=7
if [ $num -gt 10 ]; then
  echo "Number is greater than 10"
elif [ $num -gt 5 ]; then
  echo "Number is greater than 5"
else
  echo "Number is less than or equal to 5"
fi
```

**Explanation**:  
- First checks if num is greater than 10.
- If true, prints "Number is greater than 10".
- Otherwise, checks if num is greater than 5.
- If true, prints "Number is greater than 5".
- Otherwise, prints "Number is less than or equal to 5".

### 3.1.4 Numeric Comparison Operators

**Operators**:  
- `-eq`: Equal to
- `-ne`: Not equal to
- `-gt`: Greater than
- `-ge`: Greater than or equal to
- `-lt`: Less than
- `-le`: Less than or equal to

**Example**:
```bash
num1=10
num2=5
if [ $num1 -gt $num2 ]; then
  echo "$num1 is greater than $num2"
fi
```

### 3.1.5 String Comparison Operators

**Operators**:  
- `=`: Equal to
- `!=`: Not equal to
- `-z`: String is empty
- `-n`: String is not empty

**Example**:
```bash
string="hello"
if [ "$string" = "hello" ]; then
  echo "String is 'hello'"
fi
```

### 3.1.6 File Test Operators

**Operators**:  
- `-f`: File exists
- `-d`: Directory exists
- `-r`: File is readable
- `-w`: File is writable
- `-x`: File is executable

**Example**:
```bash
if [ -f file.txt ]; then
  echo "File 'file.txt' exists"
fi
```

### 3.1.7 Logical Operators

**Operators**:  
- `-a`: Logical AND
- `-o`: Logical OR

**Example**:
```bash
num1=10
num2=5
if [ $num1 -gt 5 -a $num2 -lt 10 ]; then
  echo "Both conditions are true"
fi
```

## 3.2 Loop Structures

**Definition**: Loop structures allow you to repeat a block of code multiple times.

### 3.2.1 for Loop

**Syntax**:
```bash
for variable in list; do
  # Code to be executed for each item in the list
done
```

**Example**:
```bash
for i in {1..5}; do
  echo "Iteration $i"
done
```

**Explanation**:  
- The for loop iterates over the numbers 1 to 5.
- For each iteration, prints "Iteration" followed by the current number.

### 3.2.2 while Loop

**Syntax**:
```bash
while [ condition ]; do
  # Code to be executed as long as condition is true
done
```

**Example**:
```bash
count=1
while [ $count -le 5 ]; do
  echo "Count is $count"
  ((count++))
done
```

**Explanation**:  
- The while loop continues as long as count is less than or equal to 5.
- It prints the current count and increments it by 1 in each iteration.
