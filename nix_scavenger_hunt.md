# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:*
/home/cabox/workspace
* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*
LICENSE  README.md  challenge_files  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md  super_scavengers.md
* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?* 
Using the -alh option shows what is in that current directory. It gives information such as the files and the ownership and permissions.
* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
a-Include directory entries whose names begin with a dot, l- A total sum of all file sizes is output on a line before the long listing. Output is one entry per line, h-When used with a long format option, use unit suffixes: Byte, Kilobyte, Megabyte, Gigabyte, Terabyte, Petabyte, and Exabyte in order to reduce the number of digits to four or fewer using powers of 2 for sizes (K=1024, M=1048576, etc.).
* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
cabox@box-codeanywhere:~$ ls /
bin  boot  dev  etc  fastboot  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
cabox@box-codeanywhere:~$ cd
cabox@box-codeanywhere:~$ /
-bash: /: Is a directory
cabox@box-codeanywhere:~$ pwd
/home/cabox
* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
cabox@box-codeanywhere:~$ cd
cabox@box-codeanywhere:~$ ~
-bash: /home/cabox: Is a directory
cabox@box-codeanywhere:~$ pwd
/home/cabox
* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
cabox@box-codeanywhere:~/workspace/challenge_files$ ls *.demo
2015_special_stuff.demo  cloaked-wookie.demo  scooter-double-mamba.demo
* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
cabox@box-codeanywhere:~/workspace/challenge_files$ cd ..
cabox@box-codeanywhere:~/workspace$ ls
LICENSE  README.md  challenge_files  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md  super_scavengers.md
cabox@box-codeanywhere:~/workspace$ pwd
/home/cabox/workspace
* Press the up arrow on your keyboard. *What just happened?*
It took me to the previous command.
* Press the up arrow a few more times. *What do you see?*
It also took me to the previous command.
* Run the `history` command. *What do you see?*
I see every command that I entired since I have started this project.

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
cabox
* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
No one else is on my system.
* How long has your system been running? Use `uptime` to see, and *paste the result here:*
18:17:03 up  1:35,  1 user,  load average: 0.00, 0.00, 0.00
* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
Shows the users, processes, starting time of the processes, cpu times, virtual memory, process id, ratio of process resident set size to the physical memory on the machine
resident set size, the non-swapped physical memory that a task has used, controlling tty,  multi-character process state, cumulative CPU time.
* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
This show alot of the same as 'ps aux'but its showing real/live time. I think the only difference is that it is showing the memory use.

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
two
* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
 01-15-2015
* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
./tmp/modi_laboriosam.txt
* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
cabox@box-codeanywhere:~/workspace/challenge_files$ grep -R WA .
./Lissie-Strosin.user:Jewessfurt, WA 00816-7241
./Britt-Erdman.user:O'Harachester, WA 37261
* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
cabox@box-codeanywhere:~/workspace/challenge_files$ grep -r Waldo .
./serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.
### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
cabox@box-codeanywhere:~/workspace/challenge_files$ ls > files.txt
cabox@box-codeanywhere:~/workspace/challenge_files$ more
Usage: more [options] file...

Options:
  -d        display help instead of ring bell
  -f        count logical, rather than screen lines
  -l        suppress pause after form feed
  -p        suppress scroll, clean screen and disblay text
  -c        suppress scroll, display text and clean line ends
  -u        suppress underlining
  -s        squeeze multiple blank lines into one
  -NUM      specify the number of lines per screenful
  +NUM      display file beginning from line number NUM
  +/STRING  display file beginning from search string match
  -V        output version information and exit
* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
I see a list of users, permissions, start times and dates.
* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
cabox@box-codeanywhere:~/workspace/challenge_files$ ps aux | grep cabox
root     14534  0.0  0.6  63876  3456 ?        Ss   21:21   0:00 sshd: cabox [priv]
cabox    14536  0.0  0.2  64008  1492 ?        S    21:21   0:00 sshd: cabox@pts/0
cabox    14537  0.0  0.3  18148  2044 pts/0    Ss   21:21   0:00 -bash
root     14551  0.0  0.6  63876  3304 ?        Ss   21:29   0:00 sshd: cabox [priv]
cabox    14553  0.0  0.2  64008  1488 ?        S    21:29   0:00 sshd: cabox@notty
cabox    14554  0.0  0.1  12776   928 ?        Ss   21:29   0:00 /usr/lib/openssh/sftp-server
cabox    14577  0.0  0.2  15520  1148 pts/0    R+   21:53   0:00 ps aux
cabox    14578  0.0  0.1   8816   748 pts/0    S+   21:53   0:00 grep --color=auto cabox