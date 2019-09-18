# linux commands
Run module(jupyter notebook) in background-	
```
nohup jupyter notebook 1>&2 &**
```
Check background processes-	
```
cat nohup.out | tail -f
```
Check size of all directories
```
du -sh *
```
List all directories	
```
ls
```
Change directory	
```
cd directory
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
Remove directory	
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

# VIM commands
Enter vim mode
```
vim filename
```
Enter edit mode - **press ESC key**
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
Copy text- **press	CTRL+SHIFT+v**


1)	“pwd”- gives the absolute path of current directory
2)	“ls”- list files in current directory
3)	“ls -a”- to see hidden files along with the other files in current directory
4)	“cd”- change directory
5)	“cd..”- go back in a directory
6)	“mkdir directoryName”- create a directory directoryName
7)	“rmdir directoryName”- to delete an empty directory
8)	“rm directoryName/fileName” – to delete a directory containing files or a particular file
9)	“rm -r directory” – to force delete a directory with files
10)	“touch fileName/dirName” – create a file/dir
11)	“man cmd”- to know manual pages of a command. Example “man touch”
12)	“cmd -help” – to know about a command
13)	“cp origin destination” – copy a file from origin to destination
14)	“mv origin destination“ – rename/move a file
15)	“locate filename” – to locate a file
16)	“echo” to add text in a file. Example - “echo hello, my name is Abhinav >> new.txt” check to edit a file
17)	“cat filename”- to view contents of a file. 1) cat file 2) edit content 3) ctrl+D to come back to cmd.
18)	“nano, vi” – inbuild editors of linux. Nano-shows keywords in different color. Can also create a file. Example – 1) open file - “nano check.txt”. 2) edit the file. 3) save using Ctrl+X then Y or N.
19)	“sudo/su”- stands for super user do. To work in root user.
20)	“df” – to check disk space
21)	“df -m” – to view space in mega bytes
22)	“du” – to check disk usage
23)	“du -sh filename” – to check disk utilization. i.e. "du -sh *" will check disk utilization of all dirs
24)	“alias”- create shortcut. Example – “alias home='cd /home/tecmint/public_html' “ will create an alias called home for /home/tecmint/public_html directory, so whenever you type home in the terminal prompt, it will put you in the /home/tecmint/public_html directory
25) "sudo yum install vim" - install vim in root mode
26)	“export”- to view all the variables
27)	“export EDITOR=/usr/bin/vim” – set vim as text editor
28)	“$PATH” – to see path variable
29)	“source” – to load any function file into the current shell
30)	“clear”- clear the screen
31)		“ctrl+shift+p” – paste command



Amazon Linux is based on centos and centos is based on redhat
Installing anaconda-
1)	wget https://repo.continuum.io/archive/Anaconda3-5.2.0-Linux-x86_64.sh
2)	bash anaconda file.sh
3)	source .bashrc 
4)	conda update conda

Modify PATH variable-
1)	echo $PATH – to check path variable
2)	nano .bashrc – open bashrc file and edit
3)	add line in the end - export PATH="/home/ec2-user/anaconda3/bin:$PATH"
4)	press “Ctrl+X” then Y and then Enter.
5)	source .bashrc – apply changes

Remove python 2-
6)	sudo su
7)	cd /usr/bin
8)	mv python2.7 testpython2.7
9)	python --version


Installing dlib-
1)	sudo yum install gcc g++ gcc gcc-c++ cmake
2)	download boost and dlib-
a.	wget https://dl.bintray.com/boostorg/release/1.65.1/source/boost_1_65_1.tar.gz 
b.	wget http://dlib.net/files/dlib-19.7.tar.bz2 
3)	extract the packages – 
a.	tar -xvf boost_1_65_1.tar.gz
b.	tar -xvf dlib-19.7.tar.bz2
4)	remove compressed files-
a.	sudo rm boost_1_65_1.tar.gz
b.	sudo rm dlib-19.7.tar.bz2
5)	go to boost dir- cd boost_1_65_1/
6)	sudo ./bootstrap.sh — with-python=python3.6 — with-libraries=python — prefix=/usr
replace “/usr” with you directory of python. For me it is – “/rms/AI/anaconda3
7)	sudo nano project-config.jam:
this file should look like following-

path = /rms/AI/anaconda3/bin:/home/ec2-user/anaconda3/bin:/usr/local/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/home/ec2-user/.local/bin:/home/ec2-user/bin
# Boost.Build Configuration
# Automatically generated by bootstrap.sh
import option ;
import feature ;
# Compiler configuration. This definition will be used unless
# you already have defined some toolsets in your user-config.jam
# file.
if ! gcc in [ feature.values <toolset> ]
{
 using gcc ;
}
project : default-build <toolset>gcc ;
# Python configuration
import python ;
if ! [ python.configured ]
{
 #using python : 3.6 : /usr/bin/python3.6 ;
using python : 3.6 : /usr/bin/python3.6 ;
}
# List of — with-<library> and — without-<library>
# options. If left empty, all libraries will be built.
# Options specified on the command line completely
# override this variable.
libraries = — with-python ;
# These settings are equivivalent to corresponding command-line
# options.
option.set prefix : /usr ;
option.set exec-prefix : /usr ;
option.set libdir : /usr/lib ;
option.set includedir : /usr/include ;
# Stop on first error
option.set keep-going : false ;

8)	sudo ./b2
9)	export BOOST_INCLUDEDIR=/rms/AI/boost_1_65_1
10)	sudo -E python setup.py install



using another drive-
1)	go to root drive - cd /
2)	list the directories – ls
3)	now change the directory you want to use – cd dirName
mount a filesystem to a directory-
1)	cd /
2)	sudo mkdir mountpoint
