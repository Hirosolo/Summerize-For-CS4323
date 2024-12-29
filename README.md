
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

## 2.9 Problem Solutions

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
