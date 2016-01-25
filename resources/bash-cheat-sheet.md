* <up> cycle through previous commands
* <ctrl + r> search through previous commands
* `;` run two commands on one line. e.g. `npm install; npm run dev`. Both happen
* `a && b` run `b` only if `a` succeeds
* Multi line statements
```
bigCommand \\
--settings 1 \\
--all-one-line 2 \\
shiz
```
* `echo "Print this!"` -> prints things (like `console.log("Print this!")`)
* `grep` searches for text in files and returns lines which match
* `ps -ef` find running processes (processes have process id's pids)
* `kill <pid>` kills a process
* `>` take the output of the left and adds it to the right. Wipes the file if already exists.
e.g. `echo "Hello John" > myFile.txt`
* `>>` take the output of the left and adds it to the right. Adds to the file if it already exists.
* `|` pipe. Takes the output from the command on the left and passes it to the right.
e.g. `ps | grep node` looks for lines with 'node' in the output of running the `ps` command.
