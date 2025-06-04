
# Day 1: 4th June

 :tick Set up a new github account 
 :tick Set up a dev community account 
 :tick Learnt about switching between 2 different dev accounts 
 :tick Git and SSH learning

 Use the commands to check what the email and username is 
 > git config user.name 
 >
 > git config user.email 

To set the user.name and user.email run the same command but append the values you want surrounded with quotes 
 > git config user.name "<\NAME>" 
 >
 > git config user.email "<\EMAIL>"

You have 2 options to use SSH keys to handle multiple Github accounts or HTTPS 
I used SSH 

1. Generate a new SSH key for each account with the following command 
> ssh-keygen -t ed25519 -C 'your-other-email@example.com' -f ~/.ssh/id_ed25519_other
|Part | Meaning |
| --- | --- |
|ssh-keygen | The command to generate a new SSH key pair |
|-t ed25519 | Specifies the key type (Ed25519 is recommended for GitHub)|
|-C "your-other-email@example.com" | A comment (optional), often used for identification | 
|-f ~/.ssh/id_ed25519_other | File path where the key will be saved (both public and private parts will be generated when the command is ran)|

2. Add keys to the SSH Agent 
> eval "$(ssh-agent -s)"
>
> ssh-add ~/.ssh/id_ed25519_other

eval "$(ssh-agent -s)"- is a background program that starts the SSH agent 
- This keeps your private keys loaded in memory 
- This also allows you to authenticates securely to services without having to retype your passphrase 
- It will output a message like this: Agent pid 12345 
ssh-add ~/.ssh/id_ed25519_other 
- This will add your private key stored in the file id_ed25519_other 
- Its matched to a publike key you've added to your Github account 

This step is necessary when working with multiple Github accounts. 
Git needs to know which SSH key to use for which repo 
Without this steps you'll run into Permission Denied errors. 

3. In your SSH config file add 
Host github-home
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ed25519_other

  Note that you should add as the identityfile the new file generated  ~/.ssh/id_ed25519_other

Also key thing to not is Host is like the alias name so 
when cloning use this after the @ 
> i.e git clone git@<host>:<username>/repo.git
>
`git remote add origin git@github-home:techwithpetra/100DOC_Journal.git`

If you need to remove a remote git repository simply run the command:
 `git remote remove origin` 

4. Setup a new SSH key in your Github Account 

Settings -> SSH and GPG keys -> New SSH key 
- Provide a Title 
- Paste in the public SSH file content 

Alternatively you can use HTTPS, this will prompt for a username/ password (PAT) to store them per repository 

`git config credential.helper store` 