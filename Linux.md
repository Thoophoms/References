Linux Cheat Sheets

- `ssh` : connect to the linux machine.
`ssh username@IPAddress`

- `ls` : list all files in the current working directory
- `ls -l` : list all files in the current working directory nicely
- `ls -a` or `ls -al` : list all files in the current directory included the hidden files

- `pwd` : "print working directory" this will tell you the path you are currently located

- `cd` : "change directory`

- `cd /` : change directory to the root of your directory

- `cd ..` : jump back 1 directory

- `cd ` : (cd space) get back to home directory

- `touch filename.txt` : create a file

- `touch file1.txt file2.txt`: create more than 1 file

- `touch -d tomorrow newfile.txt` : create a file in the future

- `echo` : talk to yourself ... maybe lol

- `echo "message" > filename.txt " write a message in the new or existing file

## Edit the file with `nano`

- `nano filename.txt` : edit the file

- Save file

```
Ctrl X

Y

Enter
```

## Edit the file with `vim`

- `vim filename.txt` : edit the file

- `I` : to insert the text in the file

- `ESC:wq` : (w = write, q = quit) save file and exit the file

- `cat filename.txt` : Read all the message in the file

- `less filename.txt` : Read the file 1 page at a time

- `head filename.txt` : See the beginning of the file

- `tail filename.txt` : See the end of the file

- `cmp file1.txt file2.txt2` : (cmp = compare) compare 2 files to see if there are the same

- `cat file.txt | sort` : this will sort it in alphabetical orders

***Note: ***This will tell you where is it different but not how is it difference

- `diff file1.txt file2.txt` : This will tell you where and how are they difference from each other

- `shed filename.txt` : when you don't want anyone to see what inside the file

___

- `mkdir folderName` : make new directory

- `cp filename.txt path` : (cp = copy) copy a file and paste to another directory

```
cp HelloWorld.txt ./Documents/Hello
```

- `mv filename.txt path` : (mv = move) move the file into another dorectory

- `rm filename.txt` : (rm = remove) delete the file

- `rmdir path` : (rmdir = remove directory) delete directory/folder

***Notes:*** If the directory not empty, use the command below

- `rmdir -r path` : (-r = recursive) delete the whole directory

```
rmdir -r myDirectory/
```

- `ln -s filename.txt linkname` : (ln = link, -s = soft) create the link to the file

```
ln -s filename.txt ThisLinkOnlyForYou
```

- `clear` : clear terminal

- `whoami` : to see your username

- `sudo useradd name` : create a new user

- `sudo adduser name` : reverse the command

- `su anotherUsername` : switch user

- `sudo passwd username` : change the password

- `cal` : Calendar

- `echo "4+5+5+7" | bc` : do the math

- `free` : See how much memory you have left

- `df` : see how much disk space you have left

- `df -H` : display disk space usage in a human-readable format (i.e., using units like MB, GB) across all mounted filesystems.

- `history` : see all history in the terminal

- `sudo reboot` : reboot

- `sudo shutdown` : shutdown in 1 minute

- `sudo shutdown -h now` : shutdown now

___

### Install finger

***Note:*** Before you install anything, you have to update the repository

```
sudo apt update
```

```
sudo apt install finger
```

___

- `finger username` : inspect another user

- `man xx` : the man command is a helping tool to help you with the thing you don't know

Ex. `man finger`, `man cat, 

- which xx` : will tell you the path of what you are looking for

Command Ex. `which finger`
Response Ex. `/usr/bin/finger`

- `whereis finger` : will tell you all paths of what you are looking for

Command Ex. `whereis finger`
Response Ex. `finger: /usr/bin/finger /usr/share/man/man1/finger.1.gz`

- `wget https://xxx.com/path` : get stuff from the internet

- `curl https://xxx.com/path > saveIntoThisName.txt` : download stuff from the internet as well. > is used when you want to direct that to something else like a file

- `zip newName.zip fileYouWantToZip.text` : zip file

- `unzip fileName.zip` : unzip file

- `sudo find path -name "filename*"` : find the given name file from where you are looking for

Ex. / will find from the root (find all)

```
sudo find / -name "Recipe*"
```

- `sudo find . -type f -name ".*"` : Find all hidden file

- `find . -type f -empty` : empty directory. It will list all regular files within that directory and its subdirectories that have no content (zero bytes in size).

- `find . -perm /a=x` : it will list all files where anyone (user, group, or others) has executable permission

- `chmod +x execitethis.sh` : make the file executable. Often used to make shell scripts (*.sh files) executable so they can be run directly from the command line.

-`chmod -x execitethis.sh` : remove the executable permission

- `chown username execitethis.sh` : (chown = change the owner) change the owner of the file

___

## Network Stuff

- `ip address` : see what is your ip address

- `resolvectl status` : display the current DNS (Domain Name System)

- `ping xxx.com` : used to test the reachability of a remote host. This will run forever. To exit type `Ctrl C`

- `ping -c count xxx.com` : used to test the reachability of a remote host in the given counts.

Ex. `ping -c 5 google.com`

- `ss` : displays a list of all sockets currently in use on the system

- `ss -tulpn` : display detailed information about TCP and UDP sockets, including listening ports, their associated processes, and their PID (Process ID) numbers.

```
- State: The state of the socket (LISTEN, ESTAB for established connections, etc.).
- Recv-Q and Send-Q: The amount of data waiting to be received and sent.
- Local Address : The local IP address and port number the socket is bound to.
- Peer Address : The remote IP address and port number for connected sockets.
- Process: The name and PID of the process that owns the socket.
```

 - `sudo iptables -I INPUT -p tcp -m tcp --dport 80 -j ACCEPT` : This rule allows incoming TCP traffic on port 80, which is essential for serving web content over HTTP. Without this rule, incoming connections to services like web servers (e.g., Apache, Nginx) on port 80 would be blocked by the firewall.
 
 
- `sudo ufw allow 80` : you are configuring the firewall to permit incoming TCP traffic on port 80. This is typically used for web servers like Apache or Nginx, which serve web content over HTTP.

- `uname` : display system information about the operating system and its kernel.

Ex.

``` shell
$ uname
Linux
```

- `uname -a` : displays all available system information. It provides a comprehensive overview of the system.

Ex.

``` bash
$ uname -a
Linux myhostname 5.4.0-74-generic #83-Ubuntu SMP Sat May 15 15:47:58 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux
```
___

### Neofetch

``` shell
sudo apt update
sudo apt install neofetch
```

- `neofetch` : displays information about your operating system, software, and hardware in a visually appealing way. It's often used to show off system details or for users who like to customize their command-line interface with informative displays.

___

- `ps` : display information about currently running processes. It stands for "process status"

- `ps -aux` : display more detailed information about all processes in a system, including those owned by other users (a), showing all processes (x), and displaying additional information (u).

- `top` : provides an overview of system processes, CPU usage, memory usage, and other system metrics.

___

## `kill` Command

The `kill` command in Linux is used to terminate or send signals to processes. It's a fundamental tool for managing processes from the command line.

### Basic Usage:

1. **Terminating Processes**: By default, `kill` sends the `SIGTERM` signal to a process, requesting it to terminate gracefully. For example, to kill a process with a specific PID (Process ID):
   ```
   kill PID
   ```
   Replace `PID` with the actual Process ID number.

2. **Sending Specific Signals**: You can send different signals using `kill` by specifying the signal with `-s` or using its shorthand:
   - `kill -s SIGNAL PID` or `kill -SIGNAL PID`
   - Common signals:
     - `SIGKILL` (`-9`): Forces termination of the process. This signal cannot be caught or ignored by the process.
     - `SIGTERM` (`-15`): Requests termination of the process. Allows the process to clean up before exiting.
     - `SIGINT` (`-2`): Interrupt signal, often sent by pressing `Ctrl+C` in terminal.

### Examples:

- **Send SIGTERM**: Terminate a process gracefully:
  ```
  kill 1234
  ```

- **Send SIGKILL**: Forcefully terminate a process if it doesn't respond to SIGTERM:
  ```
  kill -9 1234
  ```

___

## `pkill` Command

`pkill` is a command-line utility in Linux used to send signals to processes based on name and other attributes, rather than their process IDs (PIDs).

### Basic Usage:

1. **Terminating Processes by Name**:
   - `pkill PROCESS_NAME`: Terminates all processes whose name matches `PROCESS_NAME`.
   - Example: `pkill firefox` will terminate all instances of the Firefox web browser.

2. **Sending Signals**:
   - By default, `pkill` sends `SIGTERM` (termination signal) to matching processes.
   - You can specify a different signal using the `-SIG` or `-s SIGNAL` option. For example:
     - `pkill -9 PROCESS_NAME` or `pkill -SIGKILL PROCESS_NAME` sends the `SIGKILL` signal, forcefully terminating processes.

### Options and Examples:

- **Terminate a Process by Name**:
  ```
  pkill firefox
  ```
  This command will terminate all processes with the name "firefox".

- **Send a Specific Signal**:
  ```
  pkill -9 chrome
  ```
  This command sends the `SIGKILL` signal to terminate all processes named "chrome".

- **Match Processes by User**:
  ```
  pkill -u USERNAME
  ```
  Terminates all processes owned by the specified `USERNAME`.

___

