# VPS (Virtual Private Server):

## What is a VPS?

VPS is a slice of an overall machine that is completely **isolated** & cannot be accessed or corrupted by other parts of the machine

a VPS has its own operating system & dedicated resorces which means it has a slice of the overall memory, RAM etc... of the machine

## The difference between dedicated servers & VPS:

a dedicated server is a overall machine instead of just a slice of it

VPS is flexible based on the need of customers on a single machine but a dedicated server is not

## What is SSH (Secure Shell)?

SSH is a protocol that allows a machine to connect to another one

you can install software, start service, read files, configure etc... in your VPS via SSH on your own machine

### how do we stablish the connection between owr machine & VPS?

1. Username & Password -> Not so secure and can be easily guessed or get exposed

2. SSH Key -> SSH Key is a combination of two Keys: Private Key + Public Key <---> Keys are random character Combinations

### the command used to create a random SSH Key on windows:

ssh-keygen -t ed25519 -C "Label name" -f C:\Users\[your-username]\.ssh\[Label name]

can use a passphrase on creating a SSH Key to encode it for additional security

!!! do these steps to add you SSH to the linux machine manually

1. (on cmd) type .ssh\[Label name].pub -> shows the public SSH Key, Copy it

2. (on VPS (ubuntu)) mkdir -p ~/.ssh -> creates the .ssh directory

3. (on VPS (ubuntu)) nano ~/.ssh/authorized_keys -> paste the public ssh key here (ctrl + O -> Enter -> ctrl + X to save & exit)

for increased security:

4. chmod 700 ~/.ssh -> chmod command changes the read/editability of a directory

5. chmod 600 ~/.ssh/authorized_keys
