# Install borg
https://github.com/borgbackup/borg
```sh
curl -OL https://github.com/borgbackup/borg/releases/download/1.2.4/borg-linux64
sudo install borg-linux64 /usr/local/bin/borg
rm borg-linux64
```
# Install nix (not working)
```sh
curl -OL https://github.com/nix-community/nix-user-chroot/releases/download/1.2.2/nix-user-chroot-bin-1.2.2-x86_64-unknown-linux-musl
sudo install nix-user-chroot* /usr/local/bin/nix-user-chroot
rm nix-user-chroot*
```
```sh
mkdir -m 0755 ~/.nix
nix-user-chroot ~/.nix bash -c "sh <(curl -L https://nixos.org/nix/install) --no-daemon"
```
```sh
mkdir -p ~/.config/nix
echo "experimental-features = nix-command flakes" > ~/.config/nix/nix.conf
```
```txt
cat <<'EOF'>>~/.bashrc
if [ -z $NIX_USER_CHROOT ]; then
  NIX_USER_CHROOT=1 nix-user-chroot ~/.nix bash -l
fi
EOF
```
# Install nix method 2
```sh
sudo mkdir -p /var/nix
sudo chown -R whs /var/nix
```
```txt
# /etc/systemd/system/nix.service
[Unit]
Description=Nix
After=local-fs.target
[Service]
Type=oneshot
ExecStart=chattr -i /
ExecStart=mkdir -p /nix
ExecStart=chown -R whs /nix
ExecStart=chattr +i /
ExecStart=mount --bind /var/nix /nix
[Install]
WantedBy=multi-user.target
```
```sh
sudo systemctl enable nix
```
# Enable airplane mode
```txt
# /etc/systemd/system/airplane-mode.service
[Unit]
Description=Airplane mode
After=NetworkManager.service
[Service]
Type=oneshot
ExecStart=rfkill block all
[Install]
WantedBy=multi-user.target
```
```sh
sudo systemctl enable airplane-mode
```
# Install flatpaks
https://github.com/flatpak/flatpak/issues/5452#issuecomment-1604303145
```sh
rpm-ostree override replace https://bodhi.fedoraproject.org/updates/FEDORA-2023-cab8a89753
rpm-ostree override reset ostree-grub2 ostree-libs ostree
```
```sh
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```
```sh
flatpak install -y flathub com.gitlab.davem.ClamTk
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
# Install packer
https://github.com/hashicorp/packer
```sh
curl -O https://releases.hashicorp.com/packer/1.9.1/packer_1.9.1_linux_amd64.zip
sudo unzip -d /usr/local/bin packer_*_linux_amd64.zip packer
rm packer_*_linux_amd64.zip
```
# Install borgmatic
```sh
python -m ensurepip
pip3 install borgmatic
```

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
```sh
sudo grub2-mkconfig -o /etc/grub2-efi.cfg
```
