# Install borg
```sh
curl -OL https://github.com/borgbackup/borg/releases/download/1.2.2/borg-linux64
sudo install borg-linux64 /usr/local/bin/borg
```

flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
flatpak remote-modify --enable flathub

flatpak install flathub org.keepassxc.KeePassXC
flatpak install flathub org.filezillaproject.Filezilla

git config --global user.email hswongac@gmail.com
git config --global user.name whs

rpm-ostree install \
  https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm \
  https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm \
  ;

https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/
