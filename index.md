
## Week 2 Lab Report
### [Week 2 Report doc](https://docs.google.com/document/d/1ZJsxrCRiXRbgBpAxhTRwIIqs2-xILh4EZEXfhyADS7I/edit)

[Lab Report 1](lab-report-1-week2.html)

[Lab Report 1](https://Holden-B.github.io/CSE15-LAB-reports/lab-report-1-week2.html)


---------------------------------------------------------

> In this writeup, I will explain how to:
- Install VScode
- Remotely connect to a machine in VScode powershell
- Basic Unix commands
- Using **SCP** to move files
- Setting up an **SSH** key

------------------------------------------------------------

## **1. Install VScode**

Firstly, install [VScode](https://code.visualstudio.com/) and download for your specified Operating System.

Follow the install instructions and Open the VScode application, it should look like this:

[image](https://user-images.githubusercontent.com/103291577/162549740-91d52663-ec62-4b88-b9a1-92d3d492e755.png)



## **2. Remote Connection**

Next, We will look at how to connect remotley to the UCSD servers. This requires a personal address. 

Within VSCode:
- Open a new terminal, located at the top of the page under the terminal tab
- Within the terminal type `ssh cs15lsp22XXX@ieng6.ucsd.edu`
- (the XXX will be your own personalized letters, different for everyone)
- Hit `return` and you will be prompted with `Password:`
- Enter your password

 **Bada bing, bada boom... you're now remote connected to the server**

## **3. Trying Some UNIX commands**

**Here are some basic commands to try out**

- `ls` - lists all visible directories
- `cd ..` - go back one directory
- `ls -a` - shows all directories (even the hidden ones)
- `mkdir` + `enter a directory name` - make a directory
- `cat` + `filename`- displays the contents of the file
- Find more commands [here](https://www.geeksforgeeks.org/cat-command-in-linux-with-examples/)

## **4. move files with `SCP`**

The command `scp` means **secure copy** and is used to copy a file from one computer to another.

ie. from our personal machine to a remote access computer.

To do this, you will need **2 Terminal Windows**
- One is the remote login you just did in step 3, you can leave this one alone for now
- second, open a new terminal and go to the directory your file is located using the `cd`









