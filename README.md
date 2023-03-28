# slackup-grub
is a script which update-grub, when new Linux kernel is installed in a Slackware system, before shutdown or reboot.

1. This scipt is for lazy people who dont have a second kernel as backup in system
2. Using Grub in Slackware
3. And always forgot to update-grub when **slackpkg update;slackpkg upgrade-all** installing new kernel in their 
system.

With this script in your installation WHEN you forgot to updated grub , before reboot or shutdown it will do it for you.
If you didnt forget to update grub its not a problem, it will do it again for you because  **slackup-grub** dont trust you :D

## INSTALL
As root
```
wget https://raw.githubusercontent.com/rizitis/slackup-grub/main/slackup-grub.sh
cp slackup-grub.sh /etc/rc.d/
chmod +x /etc/rc.d/slackup-grub.sh
```

After that open with your text editor */etc/rc.d/rc.6*

and add these lines
```
# slackup-grub
if [ -x /etc/rc.d/slackup-grub.sh ]; then
   /etc/rc.d/slackup-grub.sh
fi
```
Its better in my opinion to add them before *rc.local_shutdown* call

I mean before this:
```
# Run any local shutdown scripts:
if [ -x /etc/rc.d/rc.local_shutdown ]; then
  /etc/rc.d/rc.local_shutdown stop
fi
```

Then 
```
updatedb
```

## HOWTO
First time you must run script manually to create some needed files.
```
/etc/rc.d/slackup-grub.sh
```
This first time script will create files and exit...
If you want to see how it work you can run it again...


GOOD LUCK!
