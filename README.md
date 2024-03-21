# SSH-tutorial
A simple tutorial that explains how to SSH from one machine to another.

## Pre-requisites
Before you start, make sure both of the machine are in the same subnet.

To SSH to another machine, make sure both machines installed SSH. To verify it, run this command below:

`where ssh`

In case you don't have, you must install it beforehand.

For Windows OS, you can install OpenSSH by going to Settings and search "Add optional feature". Install OpenSSH Client and OpenSSH Server.

To verify OpenSSH Client and OpenSSH Server, run this command in powershell (run in administrator):

`Get-WindowsCapability - Online | Where-Object Name -like 'OpenSSH'`

Above command should show you something like this:

```
Name          : OpenSSH.Client~~~~0.0.1.0
State         : Installed

Name          : OpenSSSH.Server~~~~0.0.1.0
State         : Installed
```

Once SSH is installed, you can continue to the next step.


## Allow SSH to run
For Windows machine, type this in powershell

`Start-Service sshd`

or

`Set-Service - Name sshd -StartupType 'Automatic'`

Difference between the both is the second one allows the machine to automatically run the SSH everytime the machine boot up.


## Get into the fun
To SSH to another machine, simply type this command:

`ssh username@ipaddress`

example: `ssh pringles@192.168.10.2`

It will ask the password and  then you are logged in.

==Happy SSH!==