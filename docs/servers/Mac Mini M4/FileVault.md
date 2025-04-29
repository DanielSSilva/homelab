# Problems with File Vault

When macOS boots, if you have [File Vault enabled](https://support.apple.com/en-gb/guide/mac-help/flvlt001/15.0/mac/15.0), you are prompted to introduce your user and password. Only after you introduce your credentials, the system boots into the actual OS and starts the apps/services. You can't even connect to the Mac through screen share.

This poses an issue in cases like unexpected reboots (i.e system crashes), or turning back on after a power loss. This because none of my services like Home Assistant or Pihole start before I unlock the Mac.

## A workaround
There's one workaround, but that doesn't totally solve the issue. If you want to do some maintenance like apply system updates or do a programed restart, you can prepopulate the file vault credentials and trigger a restart by running the following:

```bash
sudo fdesetup authrestart
```
You are then prompted to input the username and the password. After that, the system restarts and you are back into the login screen.
But keep in mind that this only allows you to access the Mac through the screen share. There's no apps starting in the background.

## The solution
The solution that I've found so far is a combination of disabling File Vault, and setting Mac to automatically log in as my user. This way, the system boots into the OS and starts the apps/services without needing to unlock it first. However, this means that if your Mac gets compromised, they can access all your data without needing to unlock it first.

### But is it ok?
I'm comfortable with this solution for 2 reasons:
- I have created two admin users: myself and `asgard`. Asgard is what will be used for everything, whereas my user is just so that I have my iCloud account enabled. This way, if something happens to this machine, I can still lock it through my iCloud.
- I'm not storing any sensitive data in this machine. No only that, but also if the machine gets physically compromised, the user still doesn't know the password.
