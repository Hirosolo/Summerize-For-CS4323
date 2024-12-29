
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
