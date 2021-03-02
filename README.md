# mhWaveEdit_flatpak
flatpak of Gtk2 based simple wave editor

#### install flathub repo and freedesktop sdk 20.08
```
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
flatpak install flathub org.freedesktop.Sdk/x86_64/20.08
```

#### clone and build flatpak from yml
```
git clone https://github.com/fastrizwaan/mhWaveEdit_flatpak.git
cd mhWaveEdit_flatpak

# build
flatpak-builder --force-clean build-dir io.github.mhWaveEdit.yml

# install 
flatpak-builder --user --install --force-clean build-dir io.github.mhWaveEdit.yml

# run
flatpak run io.github.mhWaveEdit
```

#### Build a flatpak bundle file from the above built repo:
```
flatpak-builder --repo="repo" --force-clean "build" io.github.mhWaveEdit.yml
flatpak --user remote-add --no-gpg-verify "mhWaveEdit" "repo"
flatpak build-bundle "repo" "mhWaveEdit.flatpak" io.github.mhWaveEdit  --runtime-repo="https://flathub.org/repo/flathub.flatpakrepo"

flatpak --user install mhWaveEdit.flatpak
flatpak run io.github.mhWaveEdit
```
