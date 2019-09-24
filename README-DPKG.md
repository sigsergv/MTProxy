# Build

Install required packages:

~~~~~
sudo apt install debhelper build-essential libssl-dev zlib1g-dev
~~~~~

Then build package:

~~~~~
dpkg-buildpackage -rfakeroot -b
~~~~~


# Repo notes

This repository uses original MTProto git repo as 'upstream' remote. It's rebased periodically
so my commits remain on top of upstream ones.

If you want to add upstream remote, use this command:

~~~~~
git remote add upstream https://github.com/TelegramMessenger/MTProxy.git 
~~~~~