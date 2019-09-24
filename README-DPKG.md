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

This code is stored as separate branch in the repository `https://github.com/sigsergv/MTProxy`
which is forked from upstream repo `https://github.com/TelegramMessenger/MTProxy`. Branch master
is always in sync with `TelegramMessenger/MTProxy` upstream. And branch `dpkg` periodically
rebased on master.

To add upstream remote, use this command:

~~~~~
git remote add upstream https://github.com/TelegramMessenger/MTProxy.git 
~~~~~