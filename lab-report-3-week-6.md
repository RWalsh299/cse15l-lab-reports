## Lab Report 3
# Stream lining ssh, Github from ieng6, copying directories


1.Stream line ssh:

![sshConfig](https://rwalsh299.github.io/cse15l-lab-reports/cinfigSS.png)


This is what my Config file looks like. I had to use terminal to re-cast the file from a .txt to no extension. When I created it using the notepad it was a .txt file which will cause the machine to not read it as a config file.


![sshworking](https://rwalsh299.github.io/cse15l-lab-reports/loginWorked.png)


Example with SCP:

![scp](https://rwalsh299.github.io/cse15l-lab-reports/workingSCP.png)




2.Setup Github Access from ieng6:

pub key on GitHub:
![pubKey](https://rwalsh299.github.io/cse15l-lab-reports/GHpubSSHKey.png)

private key stored on my machine:
![privKey](https://rwalsh299.github.io/cse15l-lab-reports/SSHPRIVKEY.png)


Pushing a change on the ieng server while logged in:
![push](https://rwalsh299.github.io/cse15l-lab-reports/gitPushonserver.png)


link for that commit:
[commit](https://github.com/RWalsh299/markdown-parser/commit/33e237e1064fb1eb628e1f880a705375c57489e9)


3.Copying whole directories with scp -r

Copying the whole repository to my school account:

![scptoServer](https://rwalsh299.github.io/cse15l-lab-reports/scpToServer.png)

logging to school account after scp (done in the same command line)

![toserver](https://rwalsh299.github.io/cse15l-lab-reports/scpToLogin.png)

running tests on server and showing that is passed

![toTests](https://rwalsh299.github.io/cse15l-lab-reports/logingToTests.png)

As you can see I only showed the part where I did it all in one line with multiple commands separated by ';'. i felt it would be redudant to show the process again.


