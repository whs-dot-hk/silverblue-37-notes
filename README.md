# Install borg
https://github.com/borgbackup/borg
```sh
curl -OL https://github.com/borgbackup/borg/releases/download/1.2.4/borg-linux64
sudo install borg-linux64 /usr/local/bin/borg
rm borg-linux64
```
# Install flatpaks
```sh
flatpak remote-modify --enable flathub
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```
```sh
flatpak install -y flathub com.gitlab.davem.ClamTk
flatpak install -y flathub org.filezillaproject.Filezilla
flatpak install -y flathub org.keepassxc.KeePassXC
```
```sh
rpm-ostree install \
  https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm \
  https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm \
  ;
```
```sh
rpm-ostree install \
  akmod-nvidia \
  smplayer \
  xorg-x11-drv-nvidia-cuda \
  ;
```
```sh
rpm-ostree kargs \
  --append=modprobe.blacklist=nouveau \
  --append=nvidia-drm.modeset=1 \
  --append=rd.driver.blacklist=nouveau \
  ;
```
# Install nix
```sh
sudo chattr -i /
sudo mkdir -p /nix
sudo mkdir -p /var/nix
sudo mount --bind /var/nix /nix
```
```txt
# /etc/fstab
/var/nix /nix none bind 0 0
```
```txt
# ~/.config/nix/nix.conf
experimental-features = nix-command flakes
```
```sh
curl -OL https://raw.githubusercontent.com/arkenfox/user.js/master/updater.sh
sh updater.sh -l
# 0
# y
rm updater.sh
```
```sh
rm updater.sh
```

* https://addons.mozilla.org/en-US/firefox/addon/keepassxc-browser/
* https://addons.mozilla.org/en-US/firefox/addon/multi-account-containers/
* https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/

about:preferences#privacy > Manage Exceptions
```txt
https://accounts.google.com/
```
```txt
https://github.com/
```
```txt
https://www.youtube.com/
```
```sh
rpm-ostree install \
  libguestfs-tools \
  libvirt-daemon-config-network \
  libvirt-daemon-kvm \
  qemu-kvm \
  virt-install \
  virt-manager \
  virt-viewer \
  ;
```

python -m ensurepip

pip3 install ansible

pip3 install borgmatic

curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

rpm-ostree install -y brasero

# F38
```sh
rpm-ostree override remove \
  libavcodec-free \
  libavfilter-free \
  libavformat-free \
  libavutil-free \
  libpostproc-free \
  libswresample-free \
  libswscale-free \
  --install ffmpeg
```
