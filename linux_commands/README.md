# Linux commands

## Basics

### Sudo
In some operatingsystems, the root-user will be inactive. Instead the user can get temporary root-permissions with the command *sudo*
```
sudo
```

### Exit
Exit your shell

```
exit
```

### Special characters and wildcards
There are a number of special characters that you need to know when working with the shell. These special characters will work with all the commands that you run in the shell.

**. (dot)**

A dot simply means "here". It thus indicates the current folder you are in.

**.. (two dots)**

Two dots specify the parent folder. You use it to select a folder closer to the root of the file tree.

**~ (tilde)**

Is used as an alias for the users homedirectory.

**? (questionmark wildcard)**

The questionmark wildcard is used as a wildcard character in shell commands to represent exactly one character, which can be any single character. Thus, two questionmarks in succession would represent any two characters in succession, and three question marks in succession would represent any string consisting of three characters.

*** (star wildcard) **

The most frequently used and usually the most useful wildcard is the star wildcard. The star wildcard has the broadest meaning of any of the wildcards, as it can represent zero characters, all single characters or any string.

**[] (square brackets wildcard)**

The third type of wildcard in shell commands is a pair of square brackets, which can represent any of the characters enclosed in the brackets. Thus, for example, the following would provide informaiton about all objects in the current directory that have an x, y or z:

```
file *[xyz]*
```

**\ (backslash)**

Used before special characters like space or wildcards to prevent bash from trying to "expand" them.

```
cd name\ with \ spaces
```

### Keyboard shortcuts

**Auto complete**

Write the first characters in the name and then hit the TAB-key.

**CTRL+A and CTRL+E**

Used to jump to the beginning or the end of the line in the terminal. You can also use *HOME* and *END*.

**CTRL+K**

Used to cut or delete everything after the cursor.

**CTRL+W**

Used to cut or ersasethe whole line.

**CTRL+Y**

Used to paste the command you cut with *CTRL+K* or *CTRL+W*

### Terminal history

You can use the command *history* to show all the commands you have used

```
history n
```
Where n is and optional argument that represents the number of commands you want to list. You can type *!n* to show the -nth command. Use *!!* to show the latest used command. You can also use *!-n* to choose a specific command that isn't the latest.

You can use for example *!cd* to show the last command that begins with cd.

**CTRL+R**

Used to make a reversed search in the history. If you want to repeat what you wrote the last time you used the command cat you would type:

```
[CTRL+R] cat
```

Then you can write you search and use *CTRL+R* to step backwards among the search result. Then use *RETURN* to run the command.


## Help

### -?, -h, --h, --help

### man

### info

### whatis

### apropos

### Other sources

## Shell and environment variables

### export

### printenv

## Tips and trix

### alias

### set

### echo

### script

### reset

### init=/bin/sh

## Install software

### Apt-get (Debian and Ubuntu)

### DPKG (Debian and Ubuntu)

Install a package

```
sudo dpkg -i packagefile.deb
```

List installed packages

```
sudo dpkg -l [optional pattern]
```

Remove an installed package

```
sudo dpkg -r packagename
```

### Yum (Fedora, RedHat, openSUSE)

## Manage filetree

### Move

**cd**

**ls**

**pwd**

**tree**

### Search for files

**find**

**locate**

**updatedb**

**whereis**

**which**

### Work with files and directories

**mkdir**

**rm**

**rmdir**

**mv**

**cp**

**ln**

**shred**

**du**

**file**

**stat**

**dd**

**touch**

**split**

### Tools

**mmv**

**rename**

**bash-script**

## System info

### Tools

**time**

**dmesg**

**df**

**who**

**w**

**users**

**last**

**lastlog**

**whoami**

**free**

**uptime**

**uname**

### Date, Time and Calendar

**date**

**cal**

### Partitions

**fdisk**

### /Proc

## Control system

### Eject

### Mount and dismount units

**mount**

**umount**

**smbmount**

**smbumount**

### Shutdown/restarting system

**shutdown**

**halt**

**reboot**

**CTRL+ALT+DEL**

### Manage processes

**ps**

**pstree**

**pgrep**

**top**

**kill**

**killall**

**pkill***

**skill**

**CTRL+C**

**CTRL+Z**

**jobs**

**bg**

**fg**

**nice**

**renice**

**snice**

### Manage services

**Basic concepts**

**service**

**/etc/init.d**

## Managing users

**root**

**su**

**sudo**

### Users and groups

**/etc/passwd, /etc/shadow and /etc/group**

**adduser/useradd**

**addgroup/groupadd**

**passwd**

## Tools for managing text

### Editing

**vi**

**emacs**

**nano**

**gedit, kwrite and others**

### Presenting

**head**

**tail**

**less**

**cat**

**tac**

**z*-commands**

**bz*-commands**

### Text information

**wc**

**cmp**

**diff**

**sdiff**

**diff3**

**comm**

**look**

### Text manipulation

**sort**

**join**

**cut**

**aspell**

**chcase**

**fmt**

**paste**

**expand**

**unexpand**

**uniq**

**tr**

**nl**

**sed**

**Search and replacement with Perl**

### Textconvert- and filter tools

**dos2unix**

**unix2dos**

**antiword**

**recode**

**enscript**

**figlet**

### Search and find text in files

**grep**
Used to search for text snippets in files.

Flags:
* -A: How many lines should be included after the matched text
* -B: How many lines should be included before the matched text

Example command
```
cat tmp.txt | grep -A 5 -B 5 "search phrase"
```

**rgrep**

**fgrep**

### PDF-documents

**pdftk**
Used to unite PDF-documents

Example command
```
pdftk input1.pdf input2.pdf input3.pdf cat output output.pdf
```

## Math tools

**units**

**numgrep**

**bc**

## Network

### Stats and information

**netstat**

**hostname**

**ping**

**traceroute**

**tcpdump**
tcpdump is a common packet analyzer that runs under the command line. It allows the user to display TCP/IP and other packets being transmitted or received over a network to which the computer is attached.

Example command
```
sudo tcpdump port 80 -s 0 -w capture.cap
```

**nmap**

**findsmb**

### Configuration

**ifconfig**

**ifup**

**ifdown**

**route**

### Internet tools

**host**

**dig**

**whois**

### Remote administration

**ssh**
* -p: Port on the remote host
* -X: To open windows on your computer

Example command
```
ssh -p 22 remoteuser@remotehost.domain.com
```

**screen**

### Internet software

**ftp**

**sftp**

**scp**
Used to send/retrieve files to/from a remote host.

* -P: Port

Example command
```
scp -P 22 filetoupload.tar.gz remoteuser@server.domain.com:/home/remoteuser
```

**rsync**

**wget**

**curl**
curl is a client to get files from servers using any of the supported protocols. The command is designed to work without user interaction or any kind of interactivity.

curl offers a busload of useful tricks like proxy support, user authentication, ftp upload, HTTP post, file transfer resume and more.

Example command
```
curl -d @filename "http://example.com/api/endpoint"
```

**lynx**

## Security

### Filepermissions

**Introduktion**

**chmod**

**chown**

**sticky bit**

**suid**

**chattr**

**isattr**

### Tools

**md5sum**

**sha1sum**

**pwgen**

## Archive and compress files

### tar

* -c: Create archive
* -f: Archive filename
* -v: Verbose i.e display progress while creating archive
* -x: Extract files

* -j: Filter archive through bzip2
* -z: Filter archive through gzip

Compress example
```
tar -zcvf example.tar.gz /home/exampleuser/example-folder
```

Uncompress example
```
tar -zxvf example.tar.gz
```

...

**Compression tools**

**gzip**

**bzip2**

### Zip

### Unzip

## Version Control

### Subversion

Arguments
* --username followed by the username. e.g '--username User1'

^ = The head of the repo. e.g. ''^/Misc' is the same as 'svn://server/Misc'


**Checkout**
```
svn co svn://server/Misc/trunk/Test
```

**Create a new branch**
```
svn copy svn://server/Misc/trunk/Test svn://server/Misc/branches/Test2
```

**Import changes from trunk**
```
svn merge ^/Misc/trunk/Test
```

**Reintegrate to trunk**
```
svn merge --reintegrate svn://server/Misc/branches/Test2
```

**Remove bransch**
```
svn rm svn://server/Misc/branches/Test2
```

## Schedule commands

### One-time event

**at**

**atq**

**atrm**

### Recurring events

**crontab**

**anacron**

## Send input/output between software

### Concept and definitions

### Usage

### Command substitution

**Grave accent**

**Dollar sign**

### Multiple commands at the same time

### xargs

## Regular expressions

### Shell

### Other

## MySQL ##

### Import dump ###

Import to an existing local database
```
sudo mysql -u root -p -h localhost DATABASE_NAME < data.sql
```
