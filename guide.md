##Guide on how to enable passwordless sudo:

#Step 1: Enable passwordless sudo for the administrator

First, SSH to your server. In many cases, you’ll have made this ‘passwordless’ as well, so you’ll use your private key:

`ssh -i ~/.ssh/id_rsa @`

Then start the visudo program (you’ll need to provide your password to make sudo work):

`sudo visudo`

At the bottom of this file, add the line:

`$USER ALL=(ALL) NOPASSWD: ALL`

The expression $USER denotes a shell variable automatically set to contain the current user’s username.

Save and exit. Then log out of the machine and back in. You should be able to perform sudo actions without providing your password.
