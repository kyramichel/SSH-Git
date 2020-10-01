# SSH-Git
 Connecting to GitHub with SSH


If you get these tyoe of errors when trying to add a remote:

The authenticity of host 'github.com (..)' can't be established. RSA key fingerprint is SH.... Are you sure you want to continue connecting (yes/no/[fingerprint])? yes Warning: Permanently added 'github.com,...' (RSA) to the list of known hosts. git@github.com: Permission denied (publickey). fatal: Could not read from remote repository.

Troubleshooting 

Steps:

Open Git Bash

Check for existing SSH keys:

$ ls -al ~/.ssh

If you already have, you will see:

id_rsa.pub

id_ecdsa.pub

id_ed25519.pub

If you don't, generate SSH keys (Press Enter to accept the default file location):

$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

To copy the key to clipboard:

$ clip < ~/.ssh/id_rsa.pub

Go to your account on Github, go to Settings/SSH and GPG keys/New SSH key

Paste your key there

Next, type:

$ git remote

If you see origin, remove it:

$ git remote remove origin

Check 

$ git remote

Continue with the last steps provided on your GitHub repo page

$ git commit -m " a comment"

$ git remote add origin git@github.com:USERNAME/REPONAME.git

$ git push -u origin master

See also 

https://stackoverflow.com/questions/47707922/error-the-authenticity-of-host-github-com-cant-be-established-rsa-key-finge/64159022#64159022
