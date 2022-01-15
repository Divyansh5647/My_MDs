[[OverTheWire-Bandit]] [[Tips and Tricks for Linux File Commands]]

---
# Most Popular Linux Commands

[Linux commands handbook](https://flaviocopesbooks.fra1.digitaloceanspaces.com/linux-commands-handbook.pdf)
## LEVEL-1
```
whoami                              # prints out the username using which the terminal is being accessed

man xyz                             # display the manual for the 'xyz' command
                                    # use arrow keys to scroll 1_line_AAT, spacebar for 1_page_AAT, and q to quit
                                    
clear                               # clear the previous outputs in the terminal
                                    # OR keyboard hosrtcut : ctrl + L

pwd                                 # prints out the path of the current directory

cd /alpha/docs                      # change directory to the specified directory
cd ..                               # change directory to the parent directory
cd ../..                            # change directory to the parent directory of the parent directory
cd ~                                # change directory to the home folder
cd /                                # change directory to the root folder

mkdir alpha beta                    # create 2 new folders with the specified names(with/without path)
mkdir -p alpha/a/1                  # creates nested the specified folders in one go, starting from wherever a folder in the                                           nest is not available

touch apple orange.txt              # make 2 empty files with the specified names and extensions(if any)
                                    # if the filename already exists, then it's timestamp is updated

rmdir alpha beta                    # deletes the specified folders, provided they are empty

rm alpha beta                       # deletes the specified files
rm -v alpha beta                    # deletes the specified files and prints the operations performed
rm -r alpha beta                    # deletes the specified folders and their contents
rm -i alpha beta                    # deletes the specified files, with a prompt for each file

xdg-open alpha                      # open the specified file/folder in the default program (only 'open' for Mac)

mv loung lounge                     # rename file/folder from 'loung' to 'lounge'
mv filepath1 filepath2              # move file/folder from path1 to path2, and POSSIBLY rename it also

cp filepath1 filepath2              # copy file from path1 to path2
cp -r path1 path2                   # copy folder from path1 to path2

head file -n 100                    # prints the first 100 lines of the specified file

tail file -n 100                    # prints the last 100 lines of the specified file
tail -f file                        # prints the last 10 lines, and displays live changes at the end of the file  

date                                # prints out the current date, time and timezone

echo "hey"                          # prints out "hey" in the terminal
```

## LEVEL-2
### cat
```
cat readme                          # print the contents of the specified file
cat alpha beta                      # prints the combined contents of the specified files
cat ./-thisfile                     # cat for filenames having special characters
                                    # better to use in-general
cat 'spaces in this filename'       # cat for filenames having spaces
cat spaces\ in\ this\ filename      # cat for filenames having spaces
cat -n alpha                        # cat + display line numbers
```

### less
```
less readme                         # print the contents of the specified file in a more interactive interface (VIM)
    
    q                                   # quit the interface
    up/down key                         # scroll 1_line_AAT
    b                                   # scroll up 1_page_AAT
    space                               # scroll down 1_page_AAT
    g                                   # go to the start of the file
    G                                   # go to the end of the file
    /green                              # search for 'green' in the file

```

### ls
```
ls                                  # list current directory contents
ls /inhere/                         # ls in the sub-directory named 'inhere'
ls -a                               # ls + do not ignore entries starting with .
ls -d                               # ls only for directories
ls -l                               # ls and show permissions, date-modified, owner, file size, etc.
ls -s                               # ls + print file size in blocks
ls -S                               # ls + sort by descending order of file size
ls -t                               # ls + sort by descending order of time
```

### file
```
file thisfile.txt                   # check and show the ACTUAL filetype of the file named thisfile.txt
file *                              # check and show the ACTUAL filetype of all files in the current directory
file ./*                            # check and show the ACTUAL filetype of all files in the current directory
file ./inhere/*                     # check and show the ACTUAL filetype of all files in the 'inhere' directory
```

### find
```
find .                                      # list out all files and directories (even nested) in the current directory
find . -type f                              # list out all files (even nested) in the current directory
find . -type d                              # list out all directories (even nested) in the current directory
find . -name "*.txt"                        # list out all files (even nested) having .txt extension, despite their actual file-type in the current directory
find . -name "purple"                       # list out all files (even nested) named 'purple' (CASE_SENSITIVE) in the current directory
find . -name "*purple"                      # list out all files (even nested) having 'purple' at the end of the filename (CASE_SENSITIVE) in the current directory
find . -name "purple*"                      # list out all files (even nested) having 'purple' at the start of the filename (CASE_SENSITIVE) in the current directory
find . -name "*purple*"                     # list out all files (even nested) having 'purple' somewhere in the filename (CASE_SENSITIVE) in the current directory
find . -iname "purple"                      # list out all files (even nested) named 'purple' (CASE_INSENSITIVE) in the current directory
find . -size +1G                            # list out all files (even nested) in the current directory, having size >= 1G
                                            #
                                            # -   b – 512-byte blocks (this is the default if no suffix is used)
                                            # -   c – bytes
                                            # -   w – two-byte words
                                            # -   k – Kilobytes
                                            # -   M – Megabytes
                                            # -   G – Gigabytes
                                            #
find . -size -1K                            # list out all files (even nested) in the current directory, having size <= 1K
find . -size 1M                             # list out all files (even nested) in the current directory, having size = 1M
find . -empty                               # list out all empty files (even nested) in the current directory 
find . -mmin -30                            # list out all files and directories (even nested) in the current directory, which were modified under 30 mins
find . -not -mmin -30                       # list out all files and directories (even nested) in the current directory, which were not modified under 30 mins
find . -size +100M -and -mmin -10           # and operator
find . -size +100M -exec mv '{}' xyz/ ';'   # move all files >=100M to folder named 'xyz'
find . -not -empty -type f -ls              # Display info (like file permissions) for all non-empty FILES in the current directory
find . -user vivek                          # list files and directories created by user vivek
find . -group alpha                         # list files and directories created by group alpha
```

### grep : global regular expression print
```
grep "millionth" data.txt                   # search for "millionth" anywhere in the "data.txt" file, and print the respective line
grep -w "millionth" data.txt                # search for exact "millionth" in the "data.txt" file, and print the respective line
grep -i "millionth" data.txt                # search for CASE_INSENSITIVE "millionth" in the "data.txt" file, and print the respective line
grep -n "millionth" data.txt                # search for "millionth" in the "data.txt" file, and print the respective line + line number
```

### sort
```
sort data.txt                               # displays the content of the specified file in a sorted way (without modifying the file)
sort -f data.txt                            # sort ignoring case
sort -n data.txt                            # sort numerically
sort -r data.txt                            # sort in reverse order
sort -u data.txt                            # sort and display only unique values

```

### uniq
```

```

### wc
```
wc alpha                                    # prints out the number of lines, words, bytes, and filename of the specified file
wc -l alpha                                 # prints out the number of lines and filename of the specified file
wc -w alpha                                 # prints out the number of words and filename of the specified file
wc -m alpha                                 # prints out the number of characters and filename of the specified file
wc -c alpha                                 # prints out the number of bytes and filename of the specified file
```