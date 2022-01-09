_Last updated: 1/09/22_

SSH and terminal multiplexers like [tmux](https://tmux.github.io/) and [screen](https://www.gnu.org/software/screen/) are essential tools for working on remote servers. Tools like tmux and screen allow you to start a long-running job on a remote system, close the window and SSH session and return later to the same session. See our tmux and mosh page [here](https://github.gatech.edu/crnch-rg/rogues-docs/wiki/%5BMiscellaneous%5D-Using-Mosh-to-Access-CRNCH-Resources/_edit) for more information.

Most of our systems use SSH public and private keypairs to improve their security. Usually this means you have a local password on the remote system that is used for commands like *sudo*, but you do not use this password for logins. Instead, you use a public/private keypair 

**High-level Tips:**

- Use a public/private keypair with a ***passphrase***, especially for keys that you will reuse. The tutorials below will show you how to set this up. Your *public* key can be placed on remote servers while your *private* key should be kept secure.
- You can increase the security of your *private* key by learning to use SSH agent forwarding. See below for more details.
- Use a tool like **[Keychain](http://www.funtoo.org/Keychain)** to store your *private* key and reuse it between terminals.
- Learn how to use either **tmux** or **screen**!

### Georgia Tech's VPN ###

- If you can't log in initially, don't panic! Some machines on GT's campus are behind either ECE or CS firewalls. If a machine is not responding to a simple ping, try connecting to the Georgia Tech [VPN]() and then try sshing again. 

### Understanding public/private keypairs ###

This [OpenSSH Tutorial](http://www.funtoo.org/OpenSSH_Key_Management,_Part_1) provides a very good overview of how public and private keys work as well as how to generate your own RSA keypair. There are three pages that cover 1) generating keys, 2) key management with *ssh-agent* and *keychain*, and 3) using *ssh agent forwarding* to reduce the need to copy your private key to other machines.

### File transfers with SCP and rsync ###

Files can be transferred via the [SCP](https://help.ubuntu.com/community/SSH/TransferFiles) command. Some OSes provide GUI-based tools that provide an easy-to-use interface for this. 

For large files, it is recommended to use [rsync](https://linux.die.net/man/1/rsync) (which can use SSH underneath) to copy files and show progress for large transfers, as shown in the example below. 

```
#Transfer a large tarball to the user's home directory on the CRNCH RG login server
#Note that the -e ssh flag specifies to use SSH as the remote shell, enabling SSH for copies
rsync -av --progress -e ssh largeproject.tar.gz user@rg-login.crnch.gatech.edu:~
```

### X11 Forwarding ###

To run graphical applications from a remote server on your local machine, you must use *X Forwarding*. In a Linux environment, you can usually do this by logging in with the ```-X``` flag, but other OSes require specific tools to open the forwarded application. Currently XMing and XQuartz are recommended for Windows and Linux, respectively.

### Windows-Specific Information ###

While you can use cygwin or [Bash for Windows](https://msdn.microsoft.com/en-us/commandline/wsl/about) with the Linux-specific directions, [PuTTY](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html) and [WinSCP](https://winscp.net/eng/download.php) provide GUI-based tools that allow you to SSH to remote servers and copy files to and from them.

- To generate a new key with PuTTY, see the following [guide](https://winscp.net/eng/docs/ui_puttygen#generating_a_new_key).
- You can then store and reuse that key with Pageant. To integrate Pageant with cygwin see [here](https://github.com/cuviper/ssh-pageant).
- X11 Forwarding to a Windows machine (not running Bash for Windows is enabled by [XMing](https://sourceforge.net/projects/xming/). See PuTTY-related instructions [here](http://www.geo.mtu.edu/geoschem/docs/putty_install.html).

### Linux ###

Create your key as detailed in the OpenSSH tutorial above with ```ssh-keygen -t rsa```. You then can copy your public key (`id_rsa.pub`) to the remote server and store your private key (`id_rsa`) in your local .ssh folder. 

```
jeff@mybox:~$ ls -all .ssh/ 
total 16
drwx------  2 jeff jeff 4096 Oct  5 17:23 .
drwxr-xr-x 19 jeff jeff 4096 Oct  7 12:52 ..
-rw-------  1 jeff jeff  395 Oct  5 17:23 authorized_keys
-rw-------  1 jeff jeff 1743 Oct 1  2015 id_rsa
-rw-------  1 jeff jeff 1743 Oct 1  2015 id_rsa.pub
-rw-r--r--  1 jeff jeff  444 Oct  4 12:48 known_hosts
```

- **Note:** If you add or modify files in .ssh you will need to set your permissions to 600 (for private files) or 644 (for public files). Otherwise you may not be able to log in.

Next, look into how to minimize typing in your passphrase for multiple logins with `ssh-agent` or [Keychain](http://www.funtoo.org/Keychain).

### Mac OS X ###

Mac OS X uses a very similar setup to Linux since it includes a standard terminal setup. The main difference with OS X is that X forwarding is enabled by [XQuartz](https://www.xquartz.org/).


### SSH Agent Forwarding ###

Agent forwarding can be used to securely copy private keys without passphrases between machines. A really useful guide can be found on
the [Github site](https://developer.github.com/guides/using-ssh-agent-forwarding/). Some tips for making sure this is working:

- Check that AgentForwarding is enabled with *sshd_config* (remote server)
- Make sure that *ssh-agent* is running (remote server)
- You may need to set agent forwarding in ```.ssh/config```. Example:

```
#Specify agent forwarding for specific servers in your local .ssh/config file
Host myremote.server.gatech.edu
  ForwardAgent yes
```

To check that it is set up and working:

1) Check that your local ssh-agent (on your laptop/desktop) is running and your key has been added:

```
$ ps aux | grep ssh-agent
gtuser         20582   0.0  0.0  4297104    284   ??  Ss    9:53AM   0:00.00 ssh-agent
#Add your local private key to be forwarded. You can set this up in your .bashrc or other login script
$ ssh-add
Identity added: /Users/gtuser/.ssh/id_rsa (/Users/gtuser/.ssh/id_rsa)
#Check that the key is added
$ ssh-add -l
4096 SHA256:U1asdg43F+.....KO6XpScJQ24tUM /Users/gtuser/.ssh/id_rsa (RSA)
```

2) Make sure that your pubkey is copied over to your remote server.

```
ssh-copy-id -f -i ~/.ssh/id_rsa remote-server.gatech.edu
```

3) Test out ssh'ing. If successful you should be able to log in and see that your key has been forwarded with ssh-add -l:

```
remote-server$:ssh-add -l
4096 SHA256:U1asdg43F+.....KO6XpScJQ24tUM /Users/gtuser/.ssh/id_rsa (RSA)
```

### SSH Config Files and Aliases ###

SSH also lets you set up configuration files to specify options for specific connections (e.g., use key1 to connect to host1 and key2 to connect to host2).

[Atlassian SSH Multiple Identities](https://confluence.atlassian.com/bitbucket/configure-multiple-ssh-identities-for-gitbash-mac-osx-linux-271943168.html)

### Miscellaneous Tips ###

- The `ServerAliveInterval` can be used to keep an SSH session alive. For more information on its use, see [here](https://forum.ivorde.com/how-to-prevent-linux-ssh-client-from-disconnecting-using-serveraliveinterval-t19451.html).
- Patrick Lavin (CSE) has shared a nice page he found for setting up ssh to work with tmux, which you can find [here](http://www.hamvocke.com/blog/a-guide-to-customizing-your-tmux-conf/).
- Marat Dukhan has also created some nice slides on using ssh [here](https://drive.google.com/file/d/0BzLfrIOaqlRLZG51N1BxcGhnNnM/view).

### Hardening your SSH Server and Connections ###

Server-side options to secure SSH can usually be found in 
`Use the `AllowUsers` option in /etc/ssh/sshd_config to 

- First of all, use SSH keypairs! You can disallow using passwords by updating the following lines: 

```
    PasswordAuthentication no
    PermitEmptyPasswords no
```

- Disable root logins: `PermitRootLogin no`
- Use the `AllowUsers` option in sshd_config to restrict who can try to log in to specific users. This prevents some pings from bots.
- Run a server like fail2ban or sshguard, which can limit repeated pinging by bots.


### Common Errors (TBD) ###

If you are having trouble connecting to a server using SSH please try the following:

- Check SSH permissions!
- Check the logs for SSH under /var/log/auth.log 

### SSH Multiplexing ###

You can also use [SSH multiplexing](https://blog.scottlowe.org/2015/12/11/using-ssh-multiplexing/) to carry multiple SSH sessions over one SSH connection. This could be useful for a node where you need to connect and disconnect frequently. As an example, here is an SSH config (`.ssh/config`) that applies SSH multiplexing to all host connections from a specific node.

```
Host *
    ControlMaster auto
    ControlPath ~/.ssh/master-%r@%h:%p.socket
    ControlPersist 10m
```

### Jump / Bounce Hosts ###

At least for OpenSSH, there is a nice technique to ease access to the back-end machines.  The config file has a ProxyJump directive that sends one ssh session through another.

Adding the following to ~/.ssh/config hides the layers.  With these, you can `ssh fpaa` and end up on the pi.  Obviously, use your user name.  I (Jason) have a different one on my laptop, so I also use the stanzas to fix it.  (Note to Emacs users: The ssh.el TRAMP pairing needs the username explicitly.)

```
Host crnch
  HostName rg-login.crnch.gatech.edu
  User eriedy3

Host fpaa
  HostName rg-fpaa-host.crnch.gatech.edu
  User eriedy3
  ProxyJump crnch

Host karrawingi-login
  HostName karrawingi-login.crnch.gatech.edu
  User eriedy3
  ProxyJump crnch

Host kn1
  Hostname n1
  User eriedy3
  ProxyJump karrawingi-login
```

With the above (modified for your username) you can scp and rsync to the Emu Chick nodes.
