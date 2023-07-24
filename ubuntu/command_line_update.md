# Update Ubuntu Server Via Command Line

Updating Ubuntu Server via command line requires only two commends. First run
the following command to update the list of all packages that need updating:

```
sudo apt-get update
```

Once that completes, run the following command to update all currently installed
packages:

```
sudo apt-get upgrade
```

There is a third option that allows for a more comprehensive update. The following 
command updates packages, but handles situations where it may be required to 
install or remove other dependencies. This is also requred before performing a 
release upgrade:

```
sudo apt dist-upgrade
```

And finally, if there is a new version of the OS available, run the following command 
after running all of the above commands:

```
sudo apt do-release-upgrade
```
