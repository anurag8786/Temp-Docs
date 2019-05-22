# Setting up GIT with SSH or Mac

While setting up GIT over Mac, the main problem which we faced was the error "Error: Permission denied (publickey)", "git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository."
 
 Though after hustling for many hours we found out the solution.
 
 When you face such an Error, do follow the below instructions:
 
 
### Verify the public key is attached to your account

You must provide your public key to GitHub to establish a secure connection.

1. Open Terminal.

2. Start SSH agent in the background.

   ``$ eval "$(ssh-agent -s)"``

   ``> Agent pid 59566``
   
3. Find and take a note of your public key fingerprint. If you're using OpenSSH 6.7 or older:

   ``$ ssh-add -l``
   ``> 2048 a0:dd:42:3c:5a:9d:e4:2a:21:52:4e:78:07:6e:c8:4d /Users/USERNAME/.ssh/id_rsa (RSA)``
   
   If you're using OpenSSH 6.8 or newer:

   ``$ ssh-add -l -E md5``
   ``> 2048 MD5:a0:dd:42:3c:5a:9d:e4:2a:21:52:4e:78:07:6e:c8:4d /Users/USERNAME/.ssh/id_rsa (RSA)``
   
4. In the upper-right corner of any page, click your profile photo, then click Settings.


5. In the user settings sidebar, click **SSH and GPG keys.**

6. Compare the list of SSH keys with the output from the ``ssh-add`` command.


If you don't see your public key in GitHub, you'll need to add your **SSH key to GitHub** to associate it with your computer. Read below:

### Adding a new SSH key to your GitHub account

Before adding a new SSH key to your GitHub account, you should have:

- Checked for existing SSH keys
- Generated a new SSH key and added it to the ssh-agent

After adding a new SSH key to your GitHub account, you can reconfigure any local repositories to use SSH.

1. Copy the SSH key to your clipboard.

    If your SSH key file has a different name than the example code, modify the filename to match your current setup. When       copying your key, don't add any newlines or whitespace.

    ``$ pbcopy < ~/.ssh/id_rsa.pub``
    
    ``# Copies the contents of the id_rsa.pub file to your clipboard``
    
    ``Tip: If pbcopy isn't working, you can locate the hidden .ssh folder, open the file in your favorite text editor, and         copy it to your clipboard.``

2. In the upper-right corner of any page, click your profile photo, then click **Settings**.

3. Settings icon in the user bar
   In the user settings sidebar, click **SSH and GPG keys.**

4. Click New SSH key or Add SSH key.

5. In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might        call this key "Personal MacBook Air".

6. Paste your key into the "Key" field.

7. Click Add **SSH key.**

8. If prompted, confirm your GitHub password.


### References:
- [https://help.github.com/en/articles/error-permission-denied-publickey](url)
- [https://help.github.com/en/articles/adding-a-new-ssh-key-to-your-github-account](url)
- [https://help.github.com/en/articles/checking-for-existing-ssh-keys](url)
- [https://help.github.com/en/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent](url)
