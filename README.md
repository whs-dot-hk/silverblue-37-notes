# Install flatpaks
```sh
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```
```sh
flatpak install -y flathub org.filezillaproject.Filezilla
flatpak install -y flathub org.keepassxc.KeePassXC
```
# Install rpmfusion
```sh
rpm-ostree install \
  https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm \
  https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm \
  ;
```
# Install nvidia driver and smplayer
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
about:preferences#privacy > Cookies and site data > Manage exceptions
```txt
https://accounts.google.com
```
```txt
https://github.com
```
```txt
https://www.youtube.com
```
# Install virt-manager
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
```sh
git config --global user.email hswongac@gmail.com
git config --global user.name whs
```
# Install packer
```sh
curl -O https://releases.hashicorp.com/packer/1.9.1/packer_1.9.1_linux_amd64.zip
sudo unzip -d /usr/local/bin packer_*_linux_amd64.zip packer
rm packer_*_linux_amd64.zip
```
python -m ensurepip

pip3 install ansible

pip3 install borgmatic

curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
# Install brasero
```sh
rpm-ostree install brasero
```
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
