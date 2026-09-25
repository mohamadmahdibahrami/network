# Configuring a new VPS:

## 1. Update the system

on ubuntu apt (Advaned Package Tool) is used to update the software

!!! use sudo at the start of command if you cant do some commands (more information on create a new user, section 2)

1. apt update -> first step to update the system is to update the !registery of packages on it

2. apt upgrade -y -> upgrades all the packets on registery (-y makes it so you dont have to confirm updates after executing the command)

3. reboot -> ...cuz why not?

## 2. Create a new, non-root user

1. adduser [any username] -> creates a new non-root user

2. usermod -aG sudo [user name] -> makes the user an admin (-aG -> Add to Group)

3. ssh-copy-id -i .ssh/[Label name].pub [user name]@[VPS IP] (!!! on Linux bash ONLY) -> gives the public ssh to the new user (use on your own pc's bash (if using windows need alt bash))

4. cat /home/[user name]/.ssh/authorized_keys -> to see if you did things right

## 3. Install & configure firewall

### Built in ubuntu's firewall:

1. ufw (Uncomplicated FireWall) -> to check if the ubuntu's firewall is preinstalled

2. apt install ufw -> install ubuntu's firewall if not installed

3. ufw allow OpenSSH -> to allow logging in via SSH

4. ufw enable -> enables the firewall (!!! DO NOT do this command if you havent done step 3 you WILL get locked out)

5. ufw status verbose -> to see the firewall is running properly

### Provider's firewall:

!!! if using the provider's firewall we cant lock ourselves out & it has an extra layer of security & it will not take our VPS's resourses all because it is running outside of our VPS

!!! inbound rules make it that the outside world need to go though firewall to connect to the VPS

!!! outbound rules make it that the VPS needs to go through firewall to connect to the outside world

1. for inbound security SSH connection uses TCP through port 22

## 4. Harden SSH

### Install & run fail2ban:

1. apt install fail2ban -> this tool watches every connection & if a connection fails too many times it will block that ip

2. nano /etc/fail2ban/jail.d/sshd.local -> to edit fail2ban's configurations as follows:

[sshd]
enabled = true
maxretry = 5
findtime = 10m -> the time frame in which the failed attepts have to be
bantime = 1h -> the amount of time the ip gets banned
ignoreip = ... -> use if you want it to ignore a fixed ip

3. cat /etc/fail2ban/jail.d/sshd.local -> to see if you did things right

4. systemctl enable --now fail2ban -> to enable the tool instantly

5. systemctl status fail2ban -> to check if its up & running

### Disable root & password login:

1. nano /etc/ssh/sshd_config -> to access the ssh coniguration file (its better not to edit the source config file)

2. nano /etc/ssh/sshd_config.d/99-hardening.conf -> the files in this folder edit the source config by alphabetic priority so if we wanna overwrite 99-... changes we can add the 98-... file in here & its contents should be as follows:

PubkeyAuthentication yes -> ensures that we can login via ssh key
PasswordAuthentication no -> disables password based login
KbdInteractiveAuthentication no
PermitEmptyPasswords no -> users cannot login without a password
PermitRootLogin no -> we cant login via root user anymore
MaxAuthTries 3
X11Forwarding no
AllowUsers [user1 user2 user3]

3. sudo sshd -t -> check if there is any configuration error

4. systemctl restart ssh -> to restart ssh & apply the changes

5. systemctl status ssh -> to see if its running properly

### making ssh login easier:

1. C:\Users\[your user]\.ssh\config -> edit this file (create it if it doesnt exist) with th following command:

Host [any name you want]
HostName [VPS ip]
User [your username]
Port 22 -> ssh is 22
IdentityFile C:\Users\[your user]\.ssh\[your private or public key]

## 5. Enable automatic upgrades

1. apt install unattended-upgrades -> install & enable a tool for automatic upgrades (it will only do basic upgrades & you need to to major upgrades yourself from time to time)

2. cat /etc/apt/apt.conf.d/20auto-upgrades ->to see if its running properly ( "1" means running)

## 6. Use Talescale

1. curl -fsSL https://tailscale.com/install.sh | sh -> command used on linux to install tailscale

---

registery = فهرست
