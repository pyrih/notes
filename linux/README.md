# Linux

## Background

### Unix

- UNIX is an operating system since the 1960’s
- Unix is a [trademarked](www.unix.org) name.
- UNIX operating system is one that
  - conforms to a set of standards
  - is registered with the governing body of the trademark.
  - If any those two requirement is not met, it can only be called Unix 'like' OS.
- Active Unix OS:
  - Hewlett Packard(HP-UX)
  - IBM AIX
  - IBM z/OS
  - Oracle Solaris
  - Apple macOS

### Linux

- Linux is Unix "like" OS.
- Linux was created around 1990's
- Linux is a [trademarked](www.linuxmark.org) name.
- Linux is the name of the OS kernel, means Linux "based" OS.
- Active Linux OS:
  - Google Android
  - Oracle Linux
    - Red Hat Enterprise Linux
    - CentOS - It is based on Red Hat Enterprise Linux
    - Fedora
  - Ubuntu Linux
  - Debian Linux

## Basic Concepts

### Kernel

- The kernel is the core of Unix or Unix "like" OS, used to communicate to the hardware.
- It has the following functions.
  - Multi-tasking
  - File reads and writes
  - Connectivity to networks and devices
  - Resource allocation

### Shell

- Provides a command-line interface where the user can execute commands.
- Each user can log into one session. use `alt+F1~F12` key to switch. (`Alt+F1` is the first session after OS boot)
- It has the following functions.
  - Interprets the user commands
  - Passes the interpreted commands to the kernel
- famous shells
  - Bourne Shell(sh)
  - Bourne-Again Shell(bash), most used shell.
  - C Shell(csh)
  - Korn Shell(ksh)

### Filesystem

- For Unix/Linux OS every thing is a file
- Types of file systems:
  - xfs : Default filesystem for many newer Linux distributions
  - ext4 : 4th extended filesystem (still used with many Linux distributions)
  - exFAT : Provides support for Microsoft’s exFAT (read + write)
  - NTFS : Provides support for Microsoft’s NTFS (read-only)
- The filesystem start at root does not has volume letter
- the directories/folders are files
- home directory `~` are for users
- the current folder shown before shell symbol, all its contain can be accessed without specify path. In short, `./` is ignored for file path.
- For file contain space use """ surround the whole path.
- Its important to remember that all Linux Operating systems are case sensitive
- linux system use forward slash `/` and the following sign for relative path.
  - `.` is the current directory
  - `..` is the previous directory
  - `~` is the home directory
  - `*` means all
- absolute path starts with `/` from root folder.
- In Linux, files that start with a dot ( . ) are considered hidden files
- Linux System has the following files structure.
  - / - the root of the file system
  - /var – variable files or files that vary frequently
  - /root/Downloads – downloads directory for the root user
  - /etc – contains system wide configuration files
  - /etc/sysconfig/iptables – the path to the iptables configuration file
  - /home – contains all other user home directories
  - /home/username – the username user home directory
  - /usr – the ‘user file system’ contains non-system critical files and binary (executable) files
  - /bin and /sbin – contain system binary files
- drag file into the terminal to get its directory.
- Files permission can be represented by a character followed by three groups of three letters.
  - `ls -al` shows the following info.
    - the first character can be `-` means file, `d` means directories, `s` means a symbolic link.
    - First group is permission for users, second is for Groups, third is for others.
    - In each group `r` is read permission, `w` is write permission, `x` is execute permission, `-` is no permission.
    - execute permission for a folder means the permission to view its content.
    - the permission string is followed by the owner name, then owner group name.
  - A permission code can be calculated, using `r`=4, `w`=2, `x`=1, `-`=0, and and them together.
  - For example, `400` means only user has read permission, so the file is private.
- Related Commands
  - `df -h` list file systems.
  - `lsblk` list block devices info.

## General Commands

- Each command will return a status after execution, run `$?` to view the status of the last command.
  - 0 means succeed, 1 means error.
  - 127 is command not found.
- Command options full name are after `--`. can use the first letter, can combine the letter after one common `-`.
- Large command output press `Q` to quit. enter `/searchContent` to search.
- Both the `| more` and the `| less` command provide paging functionality in a command line environment. For example `help | less`. shows output that can be control using up and down arrow.
- `| grep <filterString>` Grep will return only those lines in the file that contain the supplied string. For Example `cat /etc/man.config | grep MANPATH`
- `startx` start X Windows System GUI.
- `shutdown –h now` shutdown immediately.
- `shutdown –r now` restart immediately.
- `appname —version` check the current version for any app.
- `man <command name>` the man pages for Linux commands.
- `info <command name>` the info pages for certain Linux commands.
- `help <command name>` To get help with built-in shell commands use the help command
- `help` get list of built in command.
- `clear` clear screen
- `ls -al` `-l` for detail `-a` for include hidden files.
  - `ls` If no directory name is followed, it will list all of the files in the current working directory.
  - `ls /etc` it will display all files inside the `etc` folder.
  - add `\` before ls to see not colored outputs.
- `cd` Change directory to the directory followed, if nothing followed cd to home dir.
- `pwd` display the absolute path to the current working directory.
- `touch` create new file
- `basename <path>` return filename or directory portion of pathname
- `mkdir <directory path(s)>` make new dir
  - create multiple new folderName separate by space.
- `cp <source> <destination> -R`, copy files for folders, `-R` include directories.
  - `cp ~/a* ~/Documents/a` copy anything begins with a to `a` folder.
- `mv <source> <destination>` The mv command is used to move or rename files
- `rm <PathToFile> -r` remove files for folders, `-r` includes folders.
  - a folder must be empty in order to execute `rm` command.
- `rmdir` remove empty directories
- `find <fromFolderPath> -type f -iname "*.txt" 2> /dev/null`
  - `-type f` is used to locates only files
  - `-type d` is used to locates only directories
  - `-iname` for any case of the file or directory name (case insensitive)
  - `2> /dev/null` Do not display any access error message
- `route -n` for checking jumps info.
- `ifconfig eth0` will display networking information about the device named `eth0`.
  - `eth0` the number is the order in which the card has been detected, starting with a zero
- `ifconfig` will display networking information about all device.
- `system-config-network-tui` starts an interactive network configuration utility.
- `ifup eth0` set `eth0` interface up.
- `ifdown eth0` set `eth0` interface down.
- `ip addr` will display the IP address for all active network interfaces.
- `route` will display the system default gateway information
- `uname -a` Print operating system info
- `cat <file.txt>` create or read a txt file.
- `*` will return all files in the current directory in a list.
  - `*.txt` will return files with a certain extension.
- `which` print the path of the command.
- `echo` command is used to print the string or text file. Ex: `echo hello world`.
  - `echo` can be followed by a single line of string. In this case quotation marks need to be escaped by the backward slash.
  - `echo` can be followed by strings surrounded by single or double quote marks, then backward slash for the other qoute is not required. `echo "'hello world'"`
  - `-e` will enable the backslash-escaped characters like `\n`, quotation marks are required.
  - `-n` prevent adding a new line after the output is printed.
  - `echo` adds a space automatically between two adjacent arguments (in the output) by default. `echo fileA fileB fileC`.
- `diff <file1> <file2>` The diff command can be used to compare the contents of two files.
- `exit` exit the shell.
- `sleep <numberOfSecond>` pause the shell for a certain number of seconds.
- `mount <deviceTypeLocation> <folderPath>` mount a device to a folder.
- `mount <deviceTypeLocation>`. unmount a device.
- `source <FileName>`, it can be used to load any functions file into the current shell script or a command prompt. It read and executes commands from given FILENAME.
- `alias` it will list all the alias the shell current have.
  - To add new alias temperately run `alias shortcut="fullCommand"`
  - Or place them into `.bash_profile` or `.bashrc` to make it available all the time.
  - run `unalias alias_name` to remove the alias.
  - run `unalias -a` to remove all alias.

### Access Control

- `who` see current who logged in.
- `who am i` check current user name
- `su` change to root user.
- `su username` change to certain user.
- `su -` change user and redirect to default home directory after changed.
- `sudo <command>` run any command as root user. using user password.
  - when user password is entered, by default following sudo commands entered in 5 min, doesn't require any password.
  - control user to use certain command without using root password in `etc/sudoers` file.
  - `visudo` this command is used to configure sudoers file, to edit it.
    1. In the template, find the command that will be made available to users or groups.
    2. uncomment the alias, if all of the command in the same category are needed for the users or groups.
    3. after the line `root ALL=(ALL) ALL` that defines root user has all access.
    4. add `%<groupname> ALL=commandAliasNeeded`.
  - `sudo -l` list commands that are available for the current user without using root password.
  - to enable sudo log, add `Defaults logfile=/var/log/sudulog` in sudoers, using `visudo`.
- `useradd <newUsername>` create new user account and add the user to a new private group named as the username.
  - After execution, new user will be added in the `etc/passwd`. It has the following info `username:passwordLink:UserID(starting from 500):GroupID::homeDirectory:defaultShell`.
- `passwd <username>`, follow the prompt to enter and confirm password.
  - Password info will be stored in the `etc/shadow` file if the system use shadow password.
  - New account without setting password is not accessible, will show `!!` in the `etc/shadow` file.
- `groupadd <groupname>` create a new group.
  - group infos are stored in the `etc/group` file.
- `usermod -G <groupname> <username>` add user to a group.
- `chmod <permissionCode> <filePath>` change the file permission.
- `chmod <permissionCode> <folderPath> -R` change permission for the folder and all its contents.
- a permission formula can be used to replace the code.
- first character can be `u` for user, `g` for group, `o` for others and `a` for all users.
- followed by `=+` add permission, `=-` remove permission.
- followed by permission `w`, `r`, or `x`.
- Ex, `o=-rx`, remove read and execute permission for other users.
- Ex, `-rx`, remove read and execute permission for all users.
- `chown <username>.<groupname> <filePath>` change file or directory's ownership.
  - `mount /dev/cdrom /media`
- `chown <username>.<groupname> <folderPath> -R` change ownership for directory and all files under it.
  - `umount /dev/cdrom`

## Tools

### Init and Run Level

- It is a daemon process that control the OS Run Level, it runs immediately after system starts up, end when the machine is shutdown.
- A Run Level is used to control the start or end of certain system services in various level of usage for security reason.
- `/etc/rc0.d`~`/etc/rc9.d` folders stores links for services and whether it needs start or kill.
- In the `rcN` folders, when a link starts with `S` it will be started in `N` run level. `K` means kill or stop the services.
- `/etc/inittab` stores information about the name and usage of all Run Levels and the system default Run Level when start up. `id:3:initdefault` means default Run Level when boot is 3.

#### Related Commands

- `init 5` set run level to 5.
- `chkconfig --list` list all services and their run level.
- `chkconfig --list <ServiceName>` list certain service and its run level info.
- `chkconfig --level 3 <ServiceName> on` set certain service is on, in certain run level.
- `service <ServiceName> start` start a service
- `service <ServiceName> stop` stop a service
- `service <ServiceName> restart` restart a service
- `service <ServiceName> status` check status of a service

### Processes

- Executing code (applications, services, etc) run as a processes.
- Each process is assigned a process ID.
- `ps` list all the user processes
- `ps aux` list all the user processes including system process.
- `ps U root` list all the root user processes
- `ps U <username>` list all processes from certain user.
- Processes are control by send signals
  - common kill signal
    - `-1` or `–SIGHUP` sends a ‘hang up’ signal. Many daemon processes are programmed to re-read their configuration when they receive a HUP signal
    - `-2` or `–SIGINT` sends the same type of signal as `CTRL+ C`. Most programs will stop. In some instances there may be some data loss.
    - `-9` or `–SIGKILL`. The OS performs an ‘unclean kill’. The process is not informed that it is ending. Most likely to result in data loss. Should only be used to stop processes that appear to be unstoppable.
    - `-15` or `–TERM`. Sends a terminate signal. Tells the process to stop what it’s doing and terminate itself. Less likely to result in data loss.
  - Use Keyboard shortcut
    - `CTRL+C` – End Process, quit gracefully
    - `CTRL+D` – End of Data, quit immediately
    - `CTRL+Z` – Stop Process or Send the Process to the background.
- When a process is running it is called a job.
  - Foreground Job - It is running, process is outputted in the console.
  - Background Job - It is running but is hidden.

#### Related Commands

- `kill -l` list kill signal options.
- `kill –s <signalNumber> <PID>` kill a process with certain kill signal, the process is indicated by PID(Process ID).
- `jobs` list all current jobs.
- `fg <jobNumber>` bring a job to the foreground.
- `<command> &` start a process and make it a background job.
- `bg` stop a foreground job first, then use this command to send it to the background.

### Environment Variables

#### PATH

- Every a command is run, it will search for the path of the commands according to the directories stored in the PATH variable.
- It will search from left to right.
- Change the PATH Variable
  - The PATH variable can be changed temperately be run `PATH=$PATH:/other/dir` to append a new directory or run `PATH=/other/dir:$PATH` to prepend.
  - It can be changed in the users `bash_profile` file. It will work for certain user only.
  - To change the PATH variable for the entire system. Modifying the `etc/profile` file.
  - Scripts in `etc/profile.d` are also responsible for changing the system environment.

#### PS1

- It is used to customize the command prompt. `PS1="custom prompt"`
- It utilizes the following special characters.
  - `\u` It will shows the current user name.
  - `\h` hostname
  - `\t` current time
  - `\s` name of the shell
  - `\n` newline
  - `\w` current working directory
  - `\W` current working directory basename
- Use `\[$(tput setaf colorCode)\]` to add color. Use `\[$(tput sgr0)\]` to reset the color to default.
  - `colorCode` uses `Xterm` number for 256 colors.

### Bash Startup Files

#### `bash_profile`

- It is located in each user's home directory.
- It will export a PATH variable that stores a list of directories.
- It is a shell script runs whenever new user login to a new seesion.

#### `bashrc`

- It is located in each user's home directory.
- It is a shell script that runs whenever the user run bash.

### rsyslog

- syslogd centralizes logging for many applications: Kernel messages, system error messages, login activity, etc.
- Typically writes log files to the `/var/log` directory
- When the configuration file is changed run `service rsyslog restart`.

#### Configuration

- The syslogd deamon is controlled via the `/etc/rsyslog.conf` file
- `rsyslog.conf` stores a list of events that will be logged by syslogd.
- Records in the `rsyslog.conf` follow this format: `facility.priorityLevel Action`.
  - For example `kern.* /var/adm/kernel` stores all log messages from kernel facility to file `/var/adm/kernel`.
- facility
  - By default, the facility for Apache is `local7`.
  - `kern` is the kernel facility.
- LogLevel options:
  - EMERG 0 System is unusable
  - ALERT 1 Action must be taken immediately
  - CRIT 2 Critical conditions
  - ERR 3 Error conditions
  - WARNING 4 Warning conditions
  - NOTICE 5 Normal but significant condition
  - INFO 6 Informational
  - DEBUG 7 Debug-level messages
- Selector Examples
  - `facility.priorityLevel` this part of the record is called selectors.
  - `kern.*` select all levels of messages from kernel facility.
  - `*.=emerg` select all `emerg` level messages.
  - `kern.info` select all kern message from info to emerg.
  - `*.=crit;kern.none` select all critical message, excluding kernal facility.
  - `kern.info;kern.!err` select all kern message from info to warn.
  - `mail.*;mail.!=info` select all mail message except info level.
- Action
  - can be sent to a local file path.
  - can be sent to a remote host `@hostname`
  - can be sent to a logged user `root,username`.

### RPM

- Red Hat Package Manager
- `rpm -q <ServiceName>` check if a service is installed.

### YUM

- It is a package manager
- `/etc/yum.conf` allows you to configure which software repositories to use globally (i.e., RedHat, Fedora, CentOS, etc…)
- `/etc/yum.repos.d/` is the configuration file for the current repositories, that will override `/etc/yum.conf` configuration.
- `cdrom.repo` configuring this file allows installation from cd-rom
- `yum list available`, see a list of available software
- `yum install package_name`, install a specific package.
- `yum groupinstall 'groupname' 'groupname2'` install package groups.
- `yum groupinstall -y 'X Window System' 'Desktop' 'Fonts'` install X window GUI
- `yum install gcc –y` Install the C compiler.
- `yum install kernel -y` and `yum install kernel-devel –y` install kernel development source.

### Vim

- `vi`, open vim.
- `vi filename.txt`, open a file with vi.
- Vi has insert mode, press i to enter insert mode, press Esc to exit.
- When out of insert mode, the following command works.
  - `:w filename.txt` save as `filename.txt` in the current folder.
  - `:wq` or `ZZ`, save and quit.
  - `:q!` quit without save.
  - `:r <file>` insert file after current line.
  - Enter `/keyword` to search the keyword in the document. It is case ssensitive

### SCP

- It is used to transfer files between local machine and remote server.
- scp `username@serverAddress:<remote file path> <local file path> -r`, `-r`means including folders
- Ex, `scp -r 000123456@exampleserver.com:/foldername/public_html/ /users/username/Downloads`

### SSH

- It is used to log in remote servers.
- Ex, `ssh -i ~/.ssh/"WordPress Key.pem" ubuntu@ec2-13-229-104-228.ap-southeast-1.compute.amazonaws.com`

### mssql

- SQL Server
- run `yum install mysql` and `yum install mysql-server` to install
- run `service mysqld start` to start.
- need `php` and `php-mysql` to work with PHP.
- Initially root username is `root`, password is empty string.
- `mysqladmin -u root password 'newpassword'` set password for root account
- `mysql -u root -p` login to root and start the mysql command interface. enter password after prompt.
- `mysql -u userName -p` login to a user account. enter password after prompt.
- `mssql -u userName -p password` connect to SQL Server with password entered.
- SQL account information is stored in the tables of the mysql database. See more about account management in SQL notes.
- The username and password in the connection string in `PHP` can be stored as text in a file in the `/etc/httpd/` folder.

### httpd

- The Apache Web Service.
- It includes a patched OpenSSL module in the current version.

#### Installation

- It can be pre-installed for most Linux.
- It can be downloaded from its [official site](http://httpd.apache.org/download.cgi)
  - Can use source code to install after compiling locally.(for Unix)
  - Can use the precompiled binary file to install.(for Windows)
    - The binary file names include the platform for which the server has been compiled.

#### Modules

- Modules are added to the server during compile-time.
- Some directives only work when the corresponding modules are included.
- Apache 2 has Multi-Processing Module(MPM) module,
  - MPM’s are platform-specific:
    - Netware mpm_netware
    - OS/2 mpmt_os2
    - Unix prefork
    - Windows mpm_winnt
  - They are responsible for:
    - binding to network ports
    - accepting requests
    - dispatching children/threads to handle the request.
- `mod-so` modules support Dynamic Shared Objects (DSO) and enable the `LoadModule` directive.

#### Configuration

- By default, configuration file is stored in `/etc/httpd/conf/httpd.conf`.
- Any changes made to the main configuration files are only recognized by Apache when it is started or restarted.
- The Apache server itself acts as user `apache` and in group `apache`.
- Directives are the title of the setting.
- Apache configuration files contain one directive per line
- A specific setting(arguments) is written after the corresponding directive.
- Directives in the configuration files are case-insensitive, arguments to directives are case-sensitive.
- Lines that begin with the hash character (#) are comments and are ignored.
- Blank lines and white space are ignored.
- The directive has two types
  - Variable Assignments `ServerRoot /etc/httpd`
  - Block Directives
  ```xml
  <VirtualHost 10.100.1.111>
    ServerAdmin	webmaster@abc.com
    DocumentRoot /path/to/content
    ServerName www.abccorp.com
    DirectoryIndex index.html
  </VirtualHost>
  ```
- Directive Scope
  - Directives placed in the main section of the configuration file apply to the entire server
  - Placing Directives in one of the following blocks restricts them in a certain scope.
    - `<Directory "/path"></Directory>` - used to enclose a group of directives which will apply only to the named directory and its sub-directories
    - `<Files "filename.html"></Files>` - provides for access control by filename.
    - `<Location></Location>` provides for access control by URL. i.e. `Alias "/cgi-bin" "/usr/bin/cgi-bin"`, `<Location "/cgi-bin"></Location>`
    - `<VirtualHost IP></VirtualHost>` - used to enclose a group of directives which will apply only to a particular virtual host
      - Apache can serve multiple websites simultaneously
      - Each site is referred to as a Virtual Host
- There are 5 kinds of status directives have, based on the module it belongs to.
  - `Core` alway available.
  - `Base` available by default.
  - `MPM` available only when MPM is included.
  - `Extension` not available by default.
  - `Experimental` compatiable, but not supported.
- Here is a list of directives.
  - [Click here](http://httpd.apache.org/docs/2.2/mod/directives.html) to see the complete list of directives.
  - `ServerRoot`
    - It defines the root folder for the Apache server at compile-time.
    - The default value is `/etc/httpd`.
  - `Listen`
    - restrict apache to respond to requests on a specific IP address
    - By default the Listen directive is set to 80
    - `Listen 10.100.1.101`, will ensure that Apache will only respond to requests destined for the IP Address 10.100.1.101
    - `Listen 10.100.1.101:80`, ensures apache only responds to requests destined for the host 10.100.1.101 on port 80
    - `Listen 80`, respond to requests on all bound IP addresses on port 80.
  - `DocumentRoot`
    - It set the folder for apache to serve web content.
    - usually has the following permission `chown root.apache /var/www/content -R; chmod 750 /var/www/content -R;`
  - `Include`
    - tell apache to look for additional configuration directives located elsewhere in the file system.
    - The file path specified may be an absolute path, or may be relative to the ServerRoot directory (/etc/httpd)
    - The config file may have an extension as `.conf` and placed in the `/etc/httpd/conf.d` directory.
    - The argument can be:
      - a file name, `Include conf/ssl.conf`
      - a wildcard match to include several files at once, `conf/vhosts/*.conf`
      - a directory, rather than a file. Apache will read all files in that directory and any subdirectory, `Include /etc/httpd/conf/vhosts/`.
    - `LoadModule` added modules to the Apache server.
  - `ErrorLog`
    - set the error log file name and path.
    - `ErrorLog logs/error_log` Without a leading, it is assumed to be relative to the ServerRoot.
    - `ErrorLog syslog` apache sends error messages to the syslogd daemon.
    - `ErrorLog syslog:local0` apache sends error messages to the syslogd daemon with facility ID as `local0`.
  - `LogLevel`
    - set log level
    - `LogLevel notice`
    - Apache uses the same Error Log Levels as `syslogd`.
      - `emerg` - A crippling error causing the system to be unusable
      - `alert` - immediate action is required
      - `crit` - Apache can usually recover, but an important service or subsystem has failed
      - `error` - an error has occurred in the content or in a request (useful in content debugging)
      - `warn` - Apache has recovered from the error and the content was delivered
      - `notice` - Normal but significant conditions (server starts and stops)
      - `info` - minor events e.g. all child processes are busy and the server may become overloaded
      - `debug` - detail the workings of the server, file openings and closings, socket management
  - `TransferLog`
    - configure the location of a server or virtual host access information log.
    - use the default Common Log Format for the access logs.
  - `LogFormat`
    - configure custom format using Combined Log format.
    - Combined Log format is an extension of the Common Log Format (CLF) standard.
    - The default format can be represent as `LogFormat “%h %l %u %t \”%r\” %>s %b”`
      - `%h` - host name or IP address of the browser making the request
      - `%l` - ident identification if available (requires an identd server)
      - `%u` - the login name as supplied by the user if available
      - `%t` - the date and time (CERN’s Common Log Format)
      - `%r` - the first line of the browser request
      - `%>s` - the status returned to the browser
      - `%b` - the number of bytes sent in the response
    - Example: `LogFormat "%h %l %u %t \"%r\" %>s %b \"%{Referer}i\" \"%{User-agent}i\"" combined`
      - `\` is used to escape `"`.
      - `combined` is a nickname chosen in the example.
      - `\n` and `\t` can be used.
    - The new format needs to output to an alias file.
  - `CustomLog`
    - apply an alias for the custom access log
    - `CustomLog logs/myhost/access_log combined`.
  - `AllowOverride`
    - It is placed inside a `<directory>` block to enable or disable the directives stored in the `.htaccess`. The `.htaccess` should be in the same folder the `<directory>` specify.
    - changes made to `.htaccess` file does not require the service to restart to be in effect and it does depend on root user. However, it is less secure than adding directives directly inside the config files.
    - It has the following options.
      - `AuthConfig` - Allows the use of authorization/authentication directives (`AuthType`, `AuthName`, `Require`)
      - `All` - any directives in the `.htaccess` will be allowed.
      - `None`- apache will not look for an `.htaccess` file in that directory and access files will be ignored.
      - `Indexes` - Allow use of the directives controlling the use and format of directory listings (List order, by file, by folder, use of icons)
      - `Limit` - Allows the use of directives controlling host access (`Allow`, `Deny` and `Order`).
      - `Options` - Allows the use of the directives controlling specific directory features (`Options` `Indexes`, `Includes`).
    - When a folder is configured to use the `.htaccess` file, all its child directory will be check to see if the `.htaccess` exists.
  - Access Control directives
    - They can be placed in the `.htaccess` files or inside any block directives. Access inside the scope of the block directive will be controlled by the following rules they define.
    - `Order Deny,Allow` default allow all, then make the Deny rules get checked first.
    - `Order Allow,Deny` default deny all, then make the Allow rules get checked first.
      - The last rules get run will override the preview rules.
    - `Allow from` and `Deny from` add rules. They can as many as need and be followed by:
      - `10.109.1.254` a full IP address.
      - `10.109` a partial IP address.
      - `10.1.0.0/255.255.0.0` IP/Mask
      - `10.109.0.0/16` CIDR
      - `example.com` URL
      - `2001::4137:9e74:8e9:66e:0:651b` IPv6
      - `all`
    ```xml
    <Directory /var/www/content/secret>
    Options +Indexes
    AuthType basic
    AuthName "Secret Files"
    AuthUserFile /etc/httpd/conf/users
    Require valid-user
    Order Deny,Allow
    Deny from all
    Allow from HostIPAddress
    </Directory>
    ```
  - `Options`
    - It should be defined after the virtual host block host in the directory block.
    - It makes the website have access to certain directory. In the virtual host config file, both of the following examples work.
      ```xml
      <Directory /var/www/vhost/files>
        Options Indexes
      </Directory>
      <Directory /var/www/vhost/files>
        Options +Indexes
      </Directory>
      ```
    - The link to the folder for the website will be `href="./files"` if `/var/www/vhost` is the DocumentRoot folder.
    - When a request is made that maps to a directory and there is no `DirectoryIndex` (e.g., index.html) in that directory, then a formatted listing of the directory will be returned to the browser.
  - `Mod_ssl` Directives
    - It is used to setup the `Mod_ssl` Directives
    - Global setting are done in the `/etc/httpd/conf.d/ssl.conf` file.
    - add the following directives inside the `<VirtualHost>` block for the server.
      - `SSLEngine on`
      - `SSLCertificateFile <CertificateFilePath>`
      - `SSLCertificateKeyFile <KeyFilePath>`
    - After changing the config file stop and start the service(not restart). enter the pass phrase for Apache to access the key file.
    - make sure the firewall allows `https` transmition.
- Apache Web Users
  - `htpasswd -c /etc/httpd/passwords username` follow the prompt to enter the password and add the user
    - `-c /etc/httpd/passwords` will to create or override the file `/etc/httpd/passwords` with a new user added later.
    - the username in the password is in plaintext, and the password is hashed.
    - A group file can be created manually that contains a list of users in a defined group.
      - `vi /etc/httpd/conf/groups` create a group file.
      - `groupname: user1 user2 user3` add users and groups in this format.
    - the password file and group file should hava permission that only allow the web server to read the file and root to read and write to it.
      - `chown root.apache /etc/httpd/passwords`
      - `chmod 640 /etc/httpd/passwords`
    - For security concern, make sure that the group file and the user file are stored outside of the document tree of the web server.
  - Add the following directives to the `<directory>` scope or in `.htaccess` file to make the authentication be in effect.
    - `AuthType` Authentication type being used. It can be,
      - `Basic` which uses Base64 encoding of credentials
      - `Digest` may have some client-side support issues
    - `AuthName "Auth Name"`
      - It is the title of the dilogue box.
      - Sent with http 401 message
      - Defines the name of the authentication realm
      - The client browser caches the username and password that you supplied, and stores it along with the authentication realm, if other resources are requested from the same realm, the same username and password can be returned.
    - `AuthUserFile` Specifies the path to the password file
    - `AuthGroupFile` Specifies the path to the group file if any
    - `Require` control who can enter password and username. It can be followed by the following options.
      - `user` followed by a username or a space delimited list of usernames
      - `group` followed by a group name or a space delimited list of groups
      - `valid-user` any user in the user file.

#### Command

- `service httpd start` or `apachectl start` start apache server.
- `service httpd restart` or `apachectl restart` to restart apache server.
  - needed whenever the server configuration is changed.
- `/etc/httpd/conf/httpd.conf` the main Apache configuration file.
  - `cat /etc/httpd/conf/httpd.conf | grep 'User'` see permission that is assigned to users in the user directives.
  - `cat /etc/httpd/conf/httpd.conf | grep 'Group'` see permission that is assigned to groups in the user directives.
  - `cat /etc/httpd/conf/httpd.conf | grep 'DocumentRoot'` see which folder is set as the default website’s content folder.
- `/etc/httpd/logs/error_log` apache server error log.
- `apachectl configtest` Or `apachectl -t`, check for syntax errors in conf files.
- `apachectl -l`, see which modules are currently compiled into the server

#### ab

- It is a benchmark tool that can be used to test how a given Apache server performs.
- `ab –Ausername:password –n30 -c3 –v1 http://urlfortesting/index.html` run test on the target URL and return result.
  - The `–A` option specifies the authentication credentials to send to the server
  - The `–n` option specifies the number of requests to be made
  - The `–c` option specifies the number of concurrent connections to be made
  - The `–v` option specifies the level of reporting (verbosity)

### openssl

- OpenSSL is an open-source command line tool that is commonly used to generate private keys, create CSRs, install your SSL/TLS certificate, and identify certificate information.
- OpenSSL version `1.0.1`, `1.0.1f`, `1.0.2-beta`, `1.0.2-beta1` are vulnerable to the HeartBleed bug.
- run `openssl genrsa -des3 -out server.ca.key 2048` to generates a Triple-DES encrypted and PEM formatted private key in the current directory. will be prompted for a pass phrase. The pass phrase will be used to encrypt the private key.
  - the private key file `server.ca.key`
- run `openssl req -new -x509 -days 365 -key server.ca.key -out 192.168.100.100.crt` and will create a self-signed x509 Certificate, valid for one year (365 days) in the current directory. Signed with private key `server.ca.key`. will be prompted to enter the pass phrase to access the private key.
  - the certificate file will be `192.168.100.100.crt`
  - Users will be prompted to enter the Distinguished Name. For some of the field enter `.` can leave it blank.

### iptables

- It is the firewall for the OS.
- Iptables is used to setup, maintain and query the filter tables.
- Filter Table has three chains
  - `Input` Packets entering system
  - `Output` Packets leaving system
  - `Forward` Packets going through system (routed)
- Each chain is a list of rules which can match a set of packets.
  - With iptables, packets traverse the chain rules until there is a match and then follow the specified target
  - No more entries in the chain are processed after a match
  - If there is no match, the chain default policy is applied
- Built-in targets have the following options for matching packets.
  - `Accept` – allow packet
  - `Drop` – drop the packet
  - `Queue` – sent to an internal application
  - `Return` – move to end of rules
    - Built-in chain - Default policy
    - User chain – return to calling chain
- One can set default action for all chains, There are two approaches in practice.
  - Allow everything by default then specifically define rules for denying
  - Allow nothing by default. then specifically define rules for allowing
- The configuration file for filter tables for IPv4 is stored in `/etc/sysconfig/iptables`
- The configuration file for filter tables for IPv6 is stored in `/etc/sysconfig/ip6tables`
- Commands
  - `service iptables start` start the firewall.
  - `service iptables save` save changes to the iptables.
  - `iptables -L -n` list on rules in the filter table.
  - `iptables -L <chainName>` list all rules for certain chain.
  - `iptables –F <chainName>` delete all rules in certain chain.
  - `iptables -A <chainName> <–i/-o> <interfaceName> -j <targetName>` append a new rule in certain chain.
    - use `-i` for input interface.
    - use `-o` for output interface.
  - `iptables -I <chainName> <insertLineNumber> <–i/-o> <interfaceName> -j <targetName>` Insert a rule in certain chain.
  - Ex: `iptables –I INPUT 3 -i eth0 –p tcp -–dport 1024:65535 -j ACCEPT` insert a rule at line 3.
    - `1024:65535` means ports 1024 through 65535.
    - `-p` is followed by the Protocol Name.
    - `-–dport` is followed by the specific port number or port range.
    - In the rules if anything is not specified, all of them will be taken into consideration.
  - `iptables -P <chainName> <defaultAction>` set the default policy.
    - chainName – `INPUT`, `OUTPUT`, `FORWARD`
    - defaultAction - `ACCEPT`, `DROP`, `REJECT`
    - Example, `iptables -P INPUT DROP` set the default policy to deny all inbound connections
- `system-config-firewall` is a graphical interface for configuring basic firewall rules.
- `system-config-firewall-tui`, start the text based system-config-firewall utility.
  - Use tab Key to move between elements.
  - Use space bar to toggle on and off.
  - Use enter key to select elements.

### crontab

- Cron is a time-based job scheduler in Unix-like computer operating systems.
- Cron tasks format:
  - It has five positional values represent time intervals.
    - from left to right each value represents `minutes`(0-59), `hours`(1-23), `day`(1-31), `month`(1-12), `day of week`(0-6, Sunday-Saturday)
    - `0 3 * * *` - command runs every 3am everyday.
    - `* * * * *` - command runs every minutes every day.
    - `*/30 * * * *` - command runs every 30 minutes.
    - `* * * * 1-5` - command runs every minutes on weekdays.
    - `0,30 * * * *` - command runs every whole hours and 30 minutes pass any hours.
  - Use [crontab guru](https://crontab.guru) - A crontab schedule translator to check the format.
- Syntax:
  - The following line will be entered to the systmen using the `crontab -e` command.
  - `* * * * * <command>` The command will be run every minutes.
  - `* * * * * <command> >> <outputlog>` The command will be run every minutes with a log.
- command:
  - `crontab -l` list all current cron tasks in the cron table for the current user.
    - `crontab -u <username> -l`list cron tasks for a certain user
    - `sudo crontab -l` list cron tasks for root user
  - `crontab -e` edit cron tasks in the cron table for the current user.
    - `crontab -u <username> -e` edit cron tasks for a certain user
    - `sudo crontab -e` edit cron tasks for root user
  - `crontab -r` remove all crontab tasks
    - optionally, delete all lines in the `crontab -r`.
