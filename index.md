
## Week 2 Lab Report
### [Week 2 Report doc](https://docs.google.com/document/d/1ZJsxrCRiXRbgBpAxhTRwIIqs2-xILh4EZEXfhyADS7I/edit)

[Lab Report 1](https://Holden-B.github.io/CSE15-LAB-reports/lab-report-1-week2.html)


---------------------------------------------------------

> In this writeup, I will explain how to:
- Install **VScode**
- Remotely connect to a machine Powershell
- Basic Unix commands
- Use **SCP** to move files
- Set up an **SSH** key

------------------------------------------------------------

## **1. Install VScode**

Firstly, install [VScode](https://code.visualstudio.com/) and download it for your specified Operating System.

Follow the install instructions and Open the VScode application, it should look like this:

[image](https://user-images.githubusercontent.com/103291577/162549740-91d52663-ec62-4b88-b9a1-92d3d492e755.png)



## **2. Remote Connection**

Next, We will look at how to connect remotley to the UCSD servers. This requires a personal address. 

Within VSCode:
- Click on `New File`
- Within the file, open a new terminal, located at the top left of the page under the terminal tab
- Within the terminal type `ssh cs15lsp22XXX@ieng6.ucsd.edu`
- (the XXX will be your own personalized letters, different for everyone)
- Hit `enter` and you will be prompted with `Password:`
- Enter your password and hit `enter`

 **Bada bing, bada boom... you're now remote connected to the server**

## **3. Trying Some UNIX commands**

**Here are some basic commands to try out**

- `ls` - lists all visible directories
- `cd` + `directoryName` - go into specified directory
- `cd ..` - go back one directory
- `ls -a` - shows all directories (even the hidden ones)
- `mkdir` + `enter a directory name` - make a directory
- `cat` + `filename`- displays the contents of the file
- Find more commands [here](https://www.geeksforgeeks.org/cat-command-in-linux-with-examples/)

## **4. Move files with `scp`**

The command `scp` means **secure copy** and is used to copy a file from one computer to another securely (duh).

ie. we could send a file from our personal machine to a remote access computer. For this example I will send the file `WhereAmI.java`

To do this, you will need **2 Terminal Windows** in *VScode*
- One terminal, ill call it **BOB** for now is the remote login you just did in step 2 and 3, you can ignore **BOB** for now
- Second, open a new terminal, we'll call it **JIM**
- on **JIM** go to the directory your file is located using the `cd` command
- `WhereAmI.java` is located on my Desktop on **JIM**
- To get to that directory, I will enter `cd desktop`
- Next, enter `scp WhereAmI.java` + `cs15lsp22XXX@ieng6.ucsd.edu`
- (once again the XXX is personal to you)
- You will then be prompted by `Password:` again, you get the gist
- Once the transfer is complete go back to the **BOB terminal**
- Input the `ls` command, you should see `WhereAmI.java`

**Congrats champ, you just securely copied a file. Don't you feel special.**

## **5. Setting up an SSH Key**

Now, `SSH` and `SCP` is really cool yeah I know. But what about the password part? It kinda sucks. It takes so long and committing passwords to memory is for squares. Fortunately theres a way around it.

Lets learn about `keys`

-











