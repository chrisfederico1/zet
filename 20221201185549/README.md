## How to Create SSH Key and Add it to Github


1) Open Terminal.
2) Paste the text below, substituting in your GitHub email address.

`$ ssh-keygen -t ed25519 -C "your_email@example.com"`


 This creates a new ssh key, using the provided email as a label.
 
 `> Generating public/private ed25519 key pair.`
 

3) When you're prompted to "Enter a file in which to save the key," press 
Enter. This accepts the default file location.

`> Enter a file in which to save the key (/home/you/.ssh/id_ed25519): [Press enter]`

4) At the prompt, type a secure passphrase. For more information, see "Working
with SSH key passphrases".

`> Enter passphrase (empty for no passphrase): [Type a passphrase]`
`> Enter same passphrase again: [Type passphrase again]`

## Adding You SSH Key to SSH Agent

Before adding a new SSH key to the ssh-agent to manage your keys, you should
have checked for existing SSH keys and generated a new SSH key.

1) Start the ssh-agent in the background.

`$ eval "$(ssh-agent -s)"`
`> Agent pid 59566`

2) Add your SSH private key to the ssh-agent. If you created your key with a 
different name, or if you are adding an existing key that has a different 
name, replace id_ed25519 in the command with the name of your private key file.

`$ ssh-add ~/.ssh/id_ed25519`


## Adding SSH Key to your GitHub Account

After adding a new SSH key to your GitHub account, you can reconfigure any
local repositories to use SSH. For more information, see "Switching remote URLs 
from HTTPS to SSH."

1) Copy the SSH public key to your clipboard.

If your SSH public key file has a different name than the example code, modify 
the filename to match your current setup. When copying your key, don't add any
newlines or whitespace.

`$ sudo apt-get install xclip`

`# Downloads and installs xclip. If you don't have apt-get, you might need 
to use another installer (like yum)`

`$ xclip -selection clipboard < ~/.ssh/id_ed25519.pub`
`# Copies the contents of the id_ed25519.pub file to your clipboard`

2) In the upper-right corner of any page, click your profile photo, then 
click Settings.

3) In the user settings sidebar, click SSH and GPG keys.
4) Click New SSH key or Add SSH key.

5) In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".
6) Paste your key into the "Key" field.
7) Click Add SSH key.
8) If prompted, confirm your GitHub password.

    #zettel #notes #git #SSH
