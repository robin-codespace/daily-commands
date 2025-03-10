# Other commands I often use

## pwd
Print the full path of current working directory.
Example:
- `pwd` - Outputs something like `/Users/username/projects`

## cd
Changes the current working directory.
Examples:
- `cd /path/to/directory` - Change to specific directory
- `cd ~` - Change to home directory
- `cd ..` - Move up one directory level
- `cd -` - Return to previous directory
- `cd` - Without arguments, changes to home directory

## mkdir 
Create new directories.
Examples:
- `mkdir new_folder` - Create a single directory
- `mkdir -p parent/child` - Create nested directory structure

## clear
Clear the terminal screen.
Example:
- `clear` - Clears screen content and moves cursor to top

## ls
List directory contents.
Examples:
- `ls` - Show contents of current directory
- `ls -l` - Show detailed information (permissions, size, modified time)
- `ls -a` - Show all files (including hidden ones)

## touch 
Create new empty files or update timestamps of existing files.
Examples:
- `touch newfile.txt` - Create a new empty file
- `touch -m existingfile.txt` - Only update file's modification time


## ssh
Secure Shell for remote system access.
Examples:
- `ssh -p 1234 username@hostname` - Basic SSH connection using specific port
- `ssh -i /path/to/key.pem username@hostname` - Connect using private key file
- `ssh -L 8080:localhost:80 username@hostname` - Local port forwarding: you access remote services locally and you control the local endpoint. For example, accessing a remote service that's behind a firewall or not directly accessible
- `ssh -R 8080:localhost:80 username@hostname` - Remote port forwarding: you expose your local service to the remote endpoint so that others can  access your local services remotely. For example, sharing development servers.


## scp
Securely copy files between hosts.
Examples:
- `scp -i /path/to/key.pem file.txt username@hostname:/path/to/dest` - Copy local file to remote using private key
- `scp username@hostname:/path/to/file.txt .` - Copy remote file to local
- `scp -r folder username@hostname:/path/to/dest` - Copy entire directory


## Check port in use
Check which process is using a specific port number.
Examples:
- `lsof -i:8080` - List all processes using port 8080 (lsof = "list open files")
- `netstat -tuln | grep 8080` - Show TCP/UDP listening ports and filter for port 8080
  - -t: TCP ports
  - -u: UDP ports 
  - -l: Only listening ports
  - -n: Show port numbers instead of names

## head
Output the first part of files.
Examples:
- `head example.txt` - Show first 10 lines by default
- `head -n 5 example.txt` - Show first 5 lines
- `head -n 5 example.txt > first_5_lines.txt` - Save first 5 lines to a new file

## tail 
Output the last part of files. Commonly used to follow log files.
Examples:
- `tail example.txt` - Show last 10 lines by default
- `tail -n 5 example.txt` - Show last 5 lines
- `tail -n 5 example.txt > last_5_line.txt` - Save last 5 lines to a new file
- `tail -f example.txt` - Follow file content in real-time as it grows
- `tail -f -n 100 example.txt` - Follow file and show last 100 lines initially