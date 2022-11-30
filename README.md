# Install borg
```sh
curl -OL https://github.com/borgbackup/borg/releases/download/1.2.2/borg-linux64
sudo install borg-linux64 /usr/local/bin/borg
```

```sh
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
flatpak remote-modify --enable flathub
```

flatpak install -y flathub org.keepassxc.KeePassXC
flatpak install -y flathub org.filezillaproject.Filezilla

git config --global user.email hswongac@gmail.com
git config --global user.name whs

rpm-ostree install \
  https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm \
  https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm \
  ;

rpm-ostree install \
  akmod-nvidia \
  smplayer \
  xorg-x11-drv-nvidia-cuda \
  ;

rpm-ostree install \
  emacs \
  vim \
  ;

```sh
curl -OL https://raw.githubusercontent.com/arkenfox/user.js/master/updater.sh
sh updater.sh -l
0
```

https://addons.mozilla.org/en-US/firefox/addon/keepassxc-browser/
https://addons.mozilla.org/en-US/firefox/addon/multi-account-containers/
https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/

about:preferences#privacy > Manage Exceptions

https://accounts.google.com/

https://github.com/

https://www.youtube.com/

rpm-ostree install \
  libguestfs-tools \
  libvirt-daemon-config-network \
  libvirt-daemon-kvm \
  qemu-kvm \
  virt-install \
  virt-manager \
  virt-viewer \
  ;

python -m ensurepip
