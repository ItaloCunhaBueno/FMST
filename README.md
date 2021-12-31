# Fedora Mirror Speed Test
A python script to test every Fedora mirror so you can decide wich one to use has the best download speed for you.

## Why ##

As I searched for a Linux distro, Fedora was the one that I liked most, specially <code>dnf</code> over <code>apt</code>.
The only problem for me was the download speed, for some reason the download speeds with <code>dnf</code> was always significantly lower than <code>apt</code>.
In search for a solution I end up doing what everyone does wich is to add <code>fastestmirror=1</code> or <code>fastestmirror=true</code> to <code>/etc/dnf/dnf.conf</code>.

The problem with <code>fastestmirror</code> is that it chooses the best mirror in terms of latency and not download speed, so it didn't solved my problem.
So I've writen this script so I can test every mirror and decide wich one has the best download speed and manually edit the following files inside <code>/etc/yum.repos.d/</code>:
  
 - fedora.repo
 - fedora-updates.repo
 - fedora-modular.repo
 - fedora-updates-modular.repo

## How to use ##

### Requirements ###

> Python 3.10
>> enlighten==1.10.2
>>
>> xmltodict==0.12.0

And the package python-dnf wich should be already installed, but if not, install it with: <code>sudo dnf install python-dnf</code>.

### Settings ###

At the begining of the script there are some variables you can adjust:
 - PACKAGE: the complete name (with extension) of a package to download, the package should be big enough so there's time to stablelize the download speed.
 - TIMEOUT: time in seconds that the download has to be completed before the script skips to the next mirror. Needs to be big enough so the download speed can stablelize.
 - CONCURRENT: how many mirrors to be evaluated at the same time.
 - SAVE_LOCATION: where to save the temporary packages and at the end, the Results.txt. Leave blank <code>''</code> for the default, wich is <code>/$home/$user/Downloads</code>

## Be advised ##

I made this script for personal use, I'm sharing it AS IS because it might help somebody. I do not pretend to give any form of help or update the script in any way.

