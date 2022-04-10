## Lab Report 1 Week 2
This will be a tutorial on how to install vs code, quickly connect to a ucsd server via using ssh, and then streamlining the process.
1. Install VS Code

[VS Code Windows](https://code.visualstudio.com/)
 If you are on mac just click the down arrow that is to the left of the 'Download' button and click mac then download. Once it is downloaded click through the setup installer. Once it is installed you should open the app and be greated with a screen that looks like this:
 (put in screen shot)

  2. Remotly connecting via ssh

First navigate over to the extension tab on the far left of VS Code (4 squares with one disconnected) search for 'Remote - ssh' download it, then 'Remote - ssh: Editing Configuration Files' download it. Now you are ready to connect via ssh to the ucsd server. Now you need to find your unique account here: [Course Account](https://sdacs.ucsd.edu/~icc/index.php).

Once you have your course account and you have reset your password for this course. open a terminal in VS Code. (Navigate to the terminal tab on the top and click new terminal)

Once you have the terminal opened type

`ssh cs15lsp22XXX@ieng6@ucsd.edu`

Replacing the XXX with your course specific account. Now when prompted enter your password that you reset for this specific course (if you have not done this yet look at the link for finding your course specific account) When prompted to continue connecting typre `yes`. After this you should see (enter screen shot) if you see this than you have done it right.

3. Trying some commands

in order to fully work in this envirnment, you should become familiar with some basic commands *cd*, *ls*, *pwd*, and *mkdir*. 
- `cd` is change directory, when you want to change the current folder you are working in type cd (then the file path of your desired directory)
- `ls` this lists all the current files in your current directory (try `ls -a` and it will show hidden folders/files)
- `pwd` which prints what present working directory you are working in
- `mkdir` which creates a new directory in your pwd

here is some examples: (insert screen shot)

4. Moving files via scp (from loacal to server)
When preforming a scp do not be logged into the server via ssh, this should be done while logged out

To move a file from your local machine to the server. first open up a terminal on your machine. Once you have navigated to the directory with your file you want to tranfer. You will be able to preform a scp. the standard syntax is: scp file server for example `scp WhereamI.java cs15lspXXX@ieng6.ucsd.edu` Remeber that the XXX should be replaced with your unique student account. You will be prompted to answer you password (enter screen shot) Once you enter it, your terminal should print as mine did, with the file name and a 100% on the right hand side.

Once this is completed you can log back into the server via ssh and check if you file is there. (insert screen shot)

5. Setting ssh auto-key




