# dropbox with systemd
Forked from RandomReaper/dropbox-systemd-user-service
----
This is a systemd service file to start up dropbox on a per user basis on boot.

The original version [joeroback/dropbox](https://github.com/joeroback/dropbox)
use system services. Here is the user service version, so users can start and
stop their own service, without `sudo`.

This assumes the user installed dropbox headless via the command line: https://www.dropbox.com/en/install?os=lnx and has dropboxd working manually (account setup...).

# Autostart


```
mkdir -p ~/.config/systemd/user/
sudo loginctl enable-linger $USER
wget -O ~/.config/systemd/user/dropbox.service https://raw.githubusercontent.com/bsnipes/dropbox-systemd-user-service/master/dropbox.service
systemctl --user daemon-reload && systemctl --user enable dropbox --now
```
