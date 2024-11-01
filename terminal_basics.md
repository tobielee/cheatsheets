## Terminal nav basics:

`~` represents the home directory usually shorthand for `/Users/username`

`man <terminal_command>` should provide a "manual" on a <terminal_command> (useful if you need more info and don't want to search online)

`.` represents current directory and `..` represents parent directory

##### useful hotkeys 
* CTRL-C: terminate current job
* CTRL-U: clear current command line text
* CTRL-A: go to beginning of command line text
* CTRL-E: go to end of command line text
* ↑: see previous command
* ↓: see next command
* tab: autocomplete directory and filenames
* q: quit subscreen and return to terminal

##### change directory (cd)
```bash
cd /path/to/directory
```
You can use `tab` key to autocomplete `/path/to/directory`

other examples:
```bash
# go to parent directory
cd ..
# go to parent directory of parent directory
cd ../..
# go to home directory
cd ~
```

##### list contents of directory (ls)
```bash
ls
ls -lha
```
* option `l` lists in long format
* option `h` lists file sizes in more "human" readable format
* option `a` lists all files (including hidden)
  
##### copying things (cp/scp/rsync)
```bash
cp path/to/file_to_copy another/path/for/file_to_copy

# copying local file to remote
scp /path/to/local/file user@remote_server:/path/on/remote/server

# copying local file to remote using key-based authentication
scp -i /path/to/private/key /path/to/local/file user@remote_server:/path/on/remote/server

# copying remote directory to local directory
scp -r username@remote.ip:/path/to/source /path/to/destination

# copying remote file to remote directory
scp -i /path/to/private/key user1@remote_server1:/path/on/remote/server1/file user2@remote_server2:/path/on/remote/server2

# Using rsync to Copy Only Changed Files
# The options -a ensures file attributes like permissions, timestamps, and symlinks are preserved;
# -v enables verbose output; -h provides human-readable output; --progress monitors progress
rsync -avh --progress /path/to/source_folder/ /path/to/destination_folder/
```

##### moving things/cut'n'paste/rename (mv)
```bash
mv source/path/to/file_to_move destination/path/for/file_to_move
```
* `mv file1 file2 dir1` move file1 and file2 to dir1
* `mv *.pdf ~/Documents` move all .pdf files from current directory to ~/Documents
  
##### deleting things (rm)
```bash
rm path/to/file_to_delete
rm -R path/to/directory_to_delete
```

##### create directory (mkdir)
```bash
mkdir path/to/directory
```

##### reading files (less)
```bash
less path/to/file
```
You can also use `vim path/to/file` if you want to read/write but you'll need to know basics of vim/vi.

##### other useful misc commands 
* pwd: print working directory
* exit: exit terminal session
* clear: clear terminal console text
* history: list of all previously executed commands
* top: list current computer processes

##### getting file/folder size info (du)

for files or folders
```bash
du -h /path/to/file
du -sh path/to/folder
```

for disk space use `df`
```bash
df -h
```

##### terminate specific job (top then kill id)

use `top` to identify PID of job

```bash
kill PID
```
to force it (if above isn't working) 
```bash
kill -9 PID
```

---

### Run R script in background

```bash
nohup Rscript your_script.R > output.log 2>&1 &
```
- `nohup`: Runs a command immune to hangups, with output to a non-tty.
- `Rscript` your_script.R: Specifies the R script to be executed.
- `> output.log`: Redirects standard output to a file named output.log.
- `2>&1`: Redirects standard error to the same file as standard output.
- `&`: Puts the command in the background. 

### Set up ssh keypair for remote server access

1. Generate rsa key pair if you don't have one already
```bash
ssh-keygen -t rsa -b 2048
```
2. Copy public key to remote server
```bash
ssh-copy-id user@remote_server
```
you will be prompted to enter password to copy id

3. You should be able to `ssh` access remote server without password prompt
```bash
ssh user@remote_server
```
