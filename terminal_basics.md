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
  
##### copying things (cp)
```bash
cp path/to/file_to_copy another/path/for/file_to_copy
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


