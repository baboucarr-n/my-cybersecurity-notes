# Software Installation Process

## Adding Software with apt-get

There are several ways to add software to a system -- one is the apt-get utility. There's also apt, but apt-get has more functionality overall.

**apt vs apt-get:** apt is the newer, more user-friendly command meant for everyday interactive use (cleaner output, progress bars). apt-get is the older, more script-friendly tool with more granular options -- a lot of automation/scripting still uses apt-get for that reason. For daily manual use, apt is usually enough; apt-get is there when you need finer control.

## Searching for a Package

Before installing anything, it's worth checking if the package actually exists in the repository first:
```
apt-cache search packageName
```
apt-cache searches through the list of all packages available in the repo.

## Installing Software

```
apt-get install packageName
```

## Removing Software

```
apt-get remove snort
```
This uninstalls the software but keeps its configuration files, so if you reinstall it later you don't have to reconfigure everything from scratch.

## Removing Config Files Too (purge)

```
apt-get purge packageName
```
This uninstalls the package AND deletes its configuration files, which makes a clean reinstall a bit more work later since nothing's saved.

## Update vs Upgrade

These are not the same thing, and mixing them up is an easy mistake:

- **update** -- refreshes the list of available packages/versions from the repository. Doesn't actually install anything new, just updates what's known to be available.
```
  apt-get update
```

- **upgrade** -- actually installs the newest versions of packages based on that updated list. Needs superuser privileges (sudo, or logged in as admin), and can take a while since it might be upgrading a lot of the system at once.
```
  sudo apt-get upgrade
```

Good habit: run update before upgrade, so you're upgrading based on the latest available info.

## Repositories and sources.list

Every Linux distro has its own repository (or set of them) -- a server hosting software built and configured specifically for that distro. Kali, for example, has its own dedicated repos stocked with hacking tools and pentesting utilities that you won't find in a general-purpose distro's repo.

These repo URLs are what's listed in the system's sources.list file, which is what apt/apt-get actually reads from when searching or installing.

## Installing Software from GitHub (when it's not in a repo)

Sometimes the tool you want isn't in any repository at all -- it's just sitting in someone's GitHub repo. To grab it:

1. Find the exact GitHub repo for the tool
2. Copy its URL
3. Clone it:
```
git clone https://github.com/user/repo.git
```

git clone copies all the files and data from that repo onto your machine. You can confirm it downloaded properly by running `ls -l` in the target directory to see the files sitting there.