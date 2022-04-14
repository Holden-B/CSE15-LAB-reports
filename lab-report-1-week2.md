
# Week 2 Lab Report
### [Week 2 Report doc](https://docs.google.com/document/d/1ZJsxrCRiXRbgBpAxhTRwIIqs2-xILh4EZEXfhyADS7I/edit)

[Lab Report 1](https://Holden-B.github.io/CSE15-LAB-reports/lab-report-1-week2.html)


---------------------------------------------------------

> In this writeup, I will explain how to:
- Install **VScode**
- Remotely connect to a machine in Powershell
- Some basic Unix commands
- Use **SCP** to move files
- Set up an **SSH** key

------------------------------------------------------------

# **1. Install VScode**

Firstly, go to [VScode](https://code.visualstudio.com/) (yeah click on the blue text) and download it for your specified Operating System.

Follow the install instructions and Open the VScode application, it should look like this:

![image](https://user-images.githubusercontent.com/103291577/162555558-2a2da46e-74b6-4eae-98ae-1a516ed8fe62.png)



# **2. Remote Connection**

#### Next, We will look at how to connect remotely to the UCSD servers. This requires a personal address. 

Within VSCode:
- Click on `New File`
- Within the file, open a new terminal, located at the top left of the page under the terminal tab
- Within the terminal type `ssh cs15lsp22XXX@ieng6.ucsd.edu`
- (the XXX will be your own personalized letters, different for everyone)
- Hit `enter` and you will be prompted with `Password:`
- Enter your password and hit `enter`

 **Bada bing, bada boom... you're now remote connected to the server**
 
 ![image](https://user-images.githubusercontent.com/103291577/162592887-2e3ea71d-ea3e-483d-9532-b2b6c68a9c9f.png)


# **3. Trying Some UNIX commands**

#### **Here are some basic commands to try out**

- `ls` - lists all visible directories
- `cd` + `directoryName` - go into specified directory
- `cd ..` - go back one directory
- `ls -a` - shows all directories (even the hidden ones)
- `mkdir` + `enter a directory name` - make a directory
- `cat` + `filename`- displays the contents of the file
- Find more commands [here](https://www.geeksforgeeks.org/cat-command-in-linux-with-examples/)

*some examples of what `ls` and `ls -a` looks like*

![image](https://user-images.githubusercontent.com/103291577/162593118-278b24e5-5459-438e-9e4b-88ea88293af4.png)


# **4. Move files with `scp`**

#### `scp` or **secure copy** and is used to copy a file from one computer to another securely (duh). We can send a file from our personal machine to a remote access machine, no thumb drive or email required. 
 
 For this example I will send the file `WhereAmI.java`

To do this, you will need **2 Terminal Windows** in *VScode*
- One terminal, ill call it **BOB** is the remote login you just did in step 2 and 3, you can ignore **BOB** for now
- Second, open a new terminal, we'll call it **JIM**
- on **JIM** go to the directory your file is located using the `cd` command
- `WhereAmI.java` is located on my Desktop on **JIM**
- To get to that directory, I will enter `cd desktop`
- Next, enter `scp WhereAmI.java` + `cs15lsp22XXX@ieng6.ucsd.edu`
- (once again the XXX is personal to you)

![image](https://user-images.githubusercontent.com/103291577/162593509-1d6940d7-8f5a-4ec9-bc58-81a946c39773.png)

- You will then be prompted by `Password:` again, you get the gist
- Once the transfer is complete go back to the **BOB terminal**
- Input the `ls` command, you should see `WhereAmI.java`

![image](https://user-images.githubusercontent.com/103291577/162593118-278b24e5-5459-438e-9e4b-88ea88293af4.png)

**Congrats champ, you just securely copied a file.**

# **5. Setting up an SSH Key**

#### Now, `SSH` and `SCP` is really cool yeah I know. But what about the password part? It kinda sucks. It takes so long and committing passwords to memory is for squares. Fortunately theres a way around it.

> Lets learn about `keys`

**Keys** are a way to bypass having to enter a password. It uses a generated password specific to your computer and communicates/authenticates your login. Here are the steps to make an `ssh` key on your local computer.

- on your **terminal** window, type `ssh-keygen`
- You will be prompted to enter a destination to save the key
- type `/Users/<userName>/.ssh/id_rsa.pub`
- it will display your **random art key image**
> something like this

![image](https://user-images.githubusercontent.com/103291577/162595367-fd83ce2e-cd7c-4f3b-bfc6-5a0e4eb78588.png)

- Next, enter `ssh-keygen -t ed25519`
- This will create a private and public key files
- private will be stored in `id_rsa`
- public will be stored in `id_rsa.pub`

**Congrats, you should now be able to ssh without entering a password**

## **6. Optimizing remote access**

#### We have already covered everything super important, although heres some tips to make commands a bit easier

- You can type **commands** in quotations after your ssh address.
- For example `ssh cs15lsp22XXX@ieng6.ucsd.edu "ls"` lists directories on your server
- Use a `;` to have multiple commands execute at the same time
- For example `javac WhereAmI.java; java WhereAmI` will compile and execute in one step
- Use the **UP ARROW** on your terminal to recall commands you have already used

**Thats all for now**







