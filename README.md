# utserver
uTorrent server for Archlinux

## What is it?
uTorrent server is a headless, single user torrent client created by BitTorrent Inc. The term "server" specifies that the software does not come with a desktop GUI. Instead one should use the web interface to 
add and manage torrents. This makes it ideal use cases such as a headless PC, server or a seedbox. uTorrent server also has the entire feature set of uTorrent on Windows and Mac and usually works better with 
NATs and firewalls as compared to other BitTorrent clients, and in many cases, faster too.

This is a build script to set up uTorrent server from http://www.utorrent.com/downloads/linux on a system running Archlinux.

## How to install?
Type the following in sequence in a terminal:

```
git clone https://github.com/sunitknandi/utserver.git
cd utserver
makepkg -si
```

Done!

## How to use?
Start/stop/restart/check the daemon with:
`sudo systemctl (start|stop|restart|status) utserver`

Enable/disable the daemon to start at boot with:
`sudo systemctl (enable|disable) utserver`

Read the logs with:
`sudo tail -f /srv/utserver/utserver.log`

If you are running uTorrent for the first time, point your browser to http://localhost:8080/gui and login with username "admin" and blank password. Once logged in you can add, edit and remove torrents from 
the web interface. You can change uTorrent settings as well as the admin credentials by clicking the gear icon. You can also change the preferences by editing `/etc/utserver.conf`

Please keep mind that once any setting is changed in the web interface, it will override any changes made in `/etc/utserver.conf`

If you ever run into a problem you can delete the directory `/srv/utserver/settings` to reset uTorrent back to its default settings or that defined in `/etc/utserver.conf`; however it is a hard reset and you 
will lose all your information and added torrents.

For more documentation, please refer to the uTorrent server manual inside the `/usr/share/doc/utserver` folder once installed.

## Why this GitHub repo?
1. The original PKGBUILD on the AUR has has certain errors/issues which are pending a fix. I have tried to fix most of the bugs.
2. I want to maintain my own until the transition from AUR 2 to AUR 4 is over.

## Credits
Credits for the initial PKGBUILD go to Frikilinux <frikilinux@gmail.com> and Carl Reinke <mindless2112@gmail.com>.
I have modified the files to make it up-to-date and as bug-free as possible.

## License
uTorrent server is non-free software and is copyrighted by BitTorrent Inc.
My PKGBUILD is licensed under the GPLv2.

## Contributing
Feel free to fork it, edit it and send me a pull request. It can greatly help in timely updates.

## Questions and suggestions
Feel free to shoot me a mail at sunitnandi834 (at) gmail (dot) com and I'll get back to you. :smile:
May the source be with you. :smile:
