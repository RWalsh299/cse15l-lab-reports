## Lab Report 1 Week 2
This will be a tutorial on how to install vs code, quickly connect to a ucsd server via using ssh, and then streamlining the process.
1. Install VS Code

[VS Code Windows](https://code.visualstudio.com/)
 If you are on mac just click the down arrow that is to the left of the 'Download' button and click mac then download. Once it is downloaded click through the setup installer. Once it is installed you should open the app and be greated with a screen that looks like this:
 ![vsSetUp](https://rwalsh299.github.io/cse15l-lab-reports/vsSetUp.png)

  2. Remotly connecting via ssh

First navigate over to the extension tab on the far left of VS Code (4 squares with one disconnected) search for 'Remote - ssh' download it, then 'Remote - ssh: Editing Configuration Files' download it. Now you are ready to connect via ssh to the ucsd server. Now you need to find your unique account here: [Course Account](https://sdacs.ucsd.edu/~icc/index.php).

![vsSetUp](https://rwalsh299.github.io/cse15l-lab-reports/vsExtensionsandTerminal.png)

Once you have your course account and you have reset your password for this course. open a terminal in VS Code. (Navigate to the terminal tab on the top and click new terminal)

Once you have the terminal opened type

`ssh cs15lsp22XXX@ieng6@ucsd.edu`

Replacing the XXX with your course specific account. Now when prompted enter your password that you reset for this specific course (if you have not done this yet look at the link for finding your course specific account) When prompted to continue connecting typre `yes`. After this you should see:
![vsSetUp](https://rwalsh299.github.io/cse15l-lab-reports/sshWorking.png) if you see this, in ther terminal window, than you have done it right.

3. Trying some commands

in order to fully work in this envirnment, you should become familiar with some basic commands `cd`, `ls`, `pwd`, and `mkdir`. 
* `cd` is change directory, when you want to change the current folder you are working in type cd (then the file path of your desired directory)
* `ls` this lists all the current files in your current directory (try `ls -a` and it will show hidden folders/files)
* `pwd` which prints what present working directory you are working in
* `mkdir` which creates a new directory in your pwd

here are some examples: ![vsSetUp](https://rwalsh299.github.io/cse15l-lab-reports/commands.png)

4. Moving files via scp (from loacal to server)
When preforming a scp do not be logged into the server via ssh, this should be done while logged out

To move a file from your local machine to the server. first open up a terminal on your machine. Once you have navigated to the directory with your file you want to tranfer. You will be able to preform a scp. the standard syntax is: scp file server for example
 
 `scp WhereamI.java cs15lspXXX@ieng6.ucsd.edu:~/`
 
Remeber that the XXX should be replaced with your unique student account. The `~/` signifies that you are saving this file to the home directory of your account on the server. You will be prompted to answer you password![vsSetUp](https://rwalsh299.github.io/cse15l-lab-reports/newfiletransfer.png) Once you enter it, your terminal should print as mine did, with the file name and a 100% on the right hand side.

Once this is completed you can log back into the server via ssh and check if you file is there. 

5. Setting ssh auto-key

Now entering your password everytime you want to connect via ssh or sent a file via scp can be very time consuming. To fix this problem we can generate a pair of `ssh` keys with the set of keys. One public key which will be stored on the server, and one private key that will be stored on your machine. (DO NOT SHARE YOUR PRIVATE KEY). Now generating the keys is very easy.
* Open up a terminal on your machine and type `ssh-keygen` it should say it is generating a key pair.
* When prompted to enter the file in which to save the key, type `/Users/(Your User Name)/.ssh/id_rsa` where (Your User Name) is your personal username on your machine.
* DO NOT ADD A PASSPHRASE JUST CLICK ENETER
* You should be prompted saying where your identification and public key has been saved along with the keys randomart
* Now ssh to the server, create a directory for the public key `mkdir .ssh`
* log out of the server and scp your public key to your account
`scp /Users/(UserName)/.ssh/id_rsa.pub cs15lsp22XXX@ieng6@ucsd.edu:~/.ssh/authorized_Keys`

![showscpworking](https://rwalsh299.github.io/cse15l-lab-reports/scp_key.png)

this will transfer your public key to the server. again make sure the filep path typed in is the file path on your personal machine and the XXX is your course specific account. 

![showsshkeyworking](https://rwalsh299.github.io/cse15l-lab-reports/keyworking.png)

As you can now see I was not prompted to input my password and I was just logged in thanks to they keys. 

6. Optimize Remote Running

There are many ways to optimize this as we have already done it once before by creating the public and private keys. 

* you can enter one command to be completed after connecting via ssh `ssh cs15lsp22XXX@ieng6.ucsd.edu "ls"`

this will print all the files in your pwd once you log in, remeber it must be quotes

* you can type multiple commands in one line seperating them by semi colons 

`cp HelloWorld.java otherFile.java; javac otherFile.java; java otherFile`

This should copy the HelloWorld file to the otherFile, complie it, and run it all in one line!

![ShowOptimization](https://rwalsh299.github.io/cse15l-lab-reports/makingitbetter.png)

Now as you can see as I connected via ssh the "ls" command executes then prints the files in my pwd, In my next command line I compiled and ran a file called "WhereAmI". These are just a few examples on how to optimize your commands. 
