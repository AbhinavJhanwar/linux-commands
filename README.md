# linux commands
Run module(jupyter notebook) in background-	
```
nohup jupyter notebook 1>&2 &**
```
Check background processes-	
```
cat nohup.out | tail -f
```
to check disk usage
```
du
```
to check disk utilization of a particular dir/file
```
du -sh filename
```
Check size of all directories
```
du -sh *
```
to check disk space
```
df
```
to view space in mega bytes
```
df -m
```
List all directories	
```
ls
```
see hidden files along with the other files in current directory
```
ls -a
```
Change directory	
```
cd directory
```
go in the previous directory
```
cd.. 
```
Install any package	
```
sudo yum install package
```
Unzip file	
```
unzip filename.zip
```
Check pid for running processes	
```
ps -eaf | grep process ex-->ps -eaf | grep jupyter
```
Kill process	
```
kill -9 pid
```
Check nvidia configuration	
```
nvidia-smi
```
create a directory
```
mkdir directoryName
```
create a file/dir
```
touch fileName/dirName
```
remove an empty directory
```
rmdir directoryName
```
Force remove directory
```
rm -r directoryname
```
Edit file	
```
vim filename
```
Check installed package location	
```
which package
```
Download a file	
```
wget link_of_file
```
Install a file	
```
bash file_name.sh
```
get the absolute path of current directory
```
pwd
```
to know manual pages of a command. Example- **man touch**
```
man cmd
```
to know about a command
```
cmd -help
```
copy a file from origin to destination
```
cp origin destination
```
rename/move a file
```
mv origin destination
```
to locate a file
```
locate filename
```
to add text in a file. Example - **echo hello, my name is Abhinav >> new.txt** check to edit a file
```
echo
```
to view contents of a file. <br>
* cat file <br>
* edit content <br>
* ctrl+D to come back to cmd
```
cat filename
```
clear the screen
```
clear
```
check path variable
```
$PATH
```
create shortcut. Below command will create an alias called home for /home/tecmint/public_html directory, so whenever you type home in the terminal prompt, it will put you in the /home/tecmint/public_html directory
```
alias home='cd /home/tecmint/public_html'
```

# VIM commands
Enter vim mode
```
vim filename
```
Enter edit mode - **press ESC key** <BR><br>
Enter insert mode	
```
:I
```
Enter visual mode	
```
:V
```
Undo changes	
```
:U
```
Paste	
```
:P
```
Copy	
```
:Y
```
Cut	
```
:D
```
Display line number	
```
:set nu
```
Set auto indentation	
```
:set autoindent
```
Search text	(for next press n)
```
:search - /"text"
```
Exit without saving	
```
:Q!
```
Quit	
```
:Q
```
Save as	
```
:W "filename"
```
Save file	
```
:W
```
Save and exit	
```
:wq
```
Copy text- **press	CTRL+SHIFT+v** <BR>
