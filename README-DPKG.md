# Build

Install required packages:

~~~~~
sudo apt install debhelper build-essential libssl-dev zlib1g-dev
~~~~~

Then build package:

~~~~~
dpkg-buildpackagre -rfakeroot -b
~~~~~

# Usage howto

Install package:

~~~
sudo dpkg -i mtproxy_1.0-1_amd64.deb
~~~

Edit configuration file `/etc/default/mtproxy` and change settings you want. This file is updated during
postinstall phase so you don't required to change option `SECRET` as it's randomly generated. Main option you should
look at is `HTTP_PORTS` - list of ports telegram clients connect to, default value is 30433.

Other options could be passed via option `OTHER_OPTIONS`, it's just a string with arbitrary server arguments.

Reload systemd daemons and start service:

~~~~~
sudo systemctl daemon-reload
sudo systemctl start mtproxy.service
~~~~~

Service status:

~~~~
sudo systemctl status mtproxy.service
~~~~

You may want to redownload system data required for mtproxy:

~~~~~
sudo /usr/bin/mtproxy-reinit
~~~~~

To enable service autostart use this command:

~~~~~
sudo systemctl enable mtproxy.service
~~~~~

Construct URL to the proxy config: `tg://proxy?server=SERVER_ADDRESS&port=PORT&secret=SECRET`

# Repo notes

This repository uses original MTProto git repo as 'upstream' remote. It's rebased periodically
so my commits remain on top of upstream ones.

You may want to add upstream remote, use this command for that case:

~~~~~
git remote add upstream https://github.com/TelegramMessenger/MTProxy.git 
~~~~~
