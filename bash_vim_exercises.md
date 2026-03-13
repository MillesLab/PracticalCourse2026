# Bash and Vim Exercises

The following exercises reinforce the essential commands and workflows
used in the shell. The goal is to become comfortable with navigation,
file handling, editing, and simple command-line pipelines.

Each task should be completed in the terminal whenever possible.

For text editing we use **vim**, since it is available on most Unix-like
systems and remains an important tool in scientific computing and remote
workflows.

### Exercise --- Basic Navigation

Open a terminal and inspect your current location.

Tasks:

1.  Print the current working directory.
2.  List the contents of the current directory.
3.  Change into a different directory.
4.  Move one level up again.
5.  Return to your home directory.

Commands that may be useful:

    pwd
    ls
    cd some_directory
    cd ..
    cd ~

Try both `ls` and `ls -l` and compare the output.

------------------------------------------------------------------------

### Exercise --- Creating Files and Directories

Create a small practice directory for the following tasks.

Tasks:

1.  Create a directory called `bash_practice`.
2.  Change into this directory.
3.  Create two subdirectories: `data` and `notes`.
4.  Create an empty file called `todo.txt`.
5.  Create an empty file called `data/sample.txt`.

Commands that may help:

    mkdir bash_practice
    cd bash_practice
    mkdir data notes
    touch todo.txt
    touch data/sample.txt

------------------------------------------------------------------------

### Exercise --- Copying, Moving, and Removing

Practice the basic file operations carefully.

Tasks:

1.  Copy `todo.txt` to `notes/todo_backup.txt`.
2.  Rename `todo.txt` to `tasks.txt`.
3.  Move `tasks.txt` into the `notes` directory.
4.  Remove `data/sample.txt`.
5.  Remove the empty `data` directory.

Commands that may help:

    cp todo.txt notes/todo_backup.txt
    mv todo.txt tasks.txt
    mv tasks.txt notes/
    rm data/sample.txt
    rmdir data

Be careful with `rm`. The shell usually does not ask for confirmation.

------------------------------------------------------------------------

### Exercise --- Viewing File Content

Create a small text file and inspect it in different ways.

Tasks:

1.  Add a few lines of text to `notes/todo_backup.txt` with a text editor.
2.  Display the full file.
3.  Display only the beginning of the file.
4.  Display only the end of the file.

Commands that may help:

    cat notes/todo_backup.txt
    head notes/todo_backup.txt
    tail notes/todo_backup.txt

You may either use an editor or shell redirection to add content.

------------------------------------------------------------------------

### Exercise --- Redirection and Appending

The shell can redirect command output into files.

Tasks:

1.  Write the output of `pwd` into a file called `where_am_i.txt`.
2.  Append the output of `ls -l` to the same file.
3.  Display the final content of the file.

Commands that may help:

    pwd > where_am_i.txt
    ls -l >> where_am_i.txt
    cat where_am_i.txt

Observe the difference between `>` and `>>`.

------------------------------------------------------------------------

### Exercise --- Searching with grep

Create a small text file containing several lines, some of which include
the word `protein` in upper and lower case.

Tasks:

1.  Search for the word `protein`.
2.  Search without case sensitivity.
3.  Print line numbers together with the matches.

Commands that may help:

    grep protein file.txt
    grep -i protein file.txt
    grep -n protein file.txt

This becomes very useful when working with log files and sequence files.

------------------------------------------------------------------------

### Exercise --- Wildcards

The shell can expand file patterns automatically.

Tasks:

1.  Create three files with the names `sample1.txt`, `sample2.txt`, and
    `sample3.txt`.
2.  List only files ending in `.txt`.
3.  Copy all `sample*.txt` files into a new directory called `backup`.

Commands that may help:

    touch sample1.txt sample2.txt sample3.txt
    ls *.txt
    mkdir backup
    cp sample*.txt backup/

---

### Exercise --- Basic Vim: Opening and Saving

Open a file in vim and practise the basic modes.

Tasks:

1. Download a pdb file with wget
   ```bash
   wget 'https://files.rcsb.org/download/1BDD.pdb' -O 1BDD.pdb
   ```

2. Open the file with vim using `vim 1BDD.pdb`
3. Scroll through the file, make some basic notes on how pdb files are structured.
4. Jump around the file (to very top and very bottom) without scrolling
5. Delete lines and add lines
6. Save and exit
7. A cheatsheet can be found here: https://vim.rtorr.com

Useful keys inside vim:

-   `i` enters insert mode
-   `Esc` returns to normal mode
-   `:w` saves (in normal mode)
-   `:q` quits (in normal mode)
-   `:wq` saves and quits
-   `dd`: Delete a line
-   `u`: Undo

Remember that vim has different modes. Most confusion at the beginning
comes from not knowing in which mode you are.

------------------------------------------------------------------------

