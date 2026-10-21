# Maintainer: haxxor <haxxor@cachyos.local>
pkgname=orcastudio-bin
pkgver=02.08.01.55.p6
pkgrel=1
pkgdesc="Bambu Studio fork with OrcaSlicer changes and restored BambuNetwork support"
arch=('x86_64')
url="https://github.com/jarczakpawel/OrcaStudio"
license=('AGPL-3.0-only')
provides=('orcastudio')
conflicts=('orcastudio')
_tag="v02.08.01.55-p6"
_file="OrcaStudio_Linux_AppImage_ubuntu24.04_amd64_${_tag#v}.AppImage"
source=("$_file::${url}/releases/download/${_tag}/$_file")
noextract=("$_file")
sha256sums=('7f1723cab14fa431b171d1e8255f3f36498e92974726110aa93a92f0f2b9cf75')

package() {
    chmod +x "$_file"
    "./$_file" --appimage-extract >/dev/null
    install -dm755 "$pkgdir/opt/orcastudio"
    cp -a squashfs-root/. "$pkgdir/opt/orcastudio/"
    rm -rf "$pkgdir/opt/orcastudio/usr"

    install -dm755 "$pkgdir/usr/bin"
    ln -s /opt/orcastudio/AppRun "$pkgdir/usr/bin/orcastudio"

    install -Dm644 squashfs-root/OrcaStudio.png "$pkgdir/usr/share/icons/hicolor/192x192/apps/orcastudio.png"

    install -dm755 "$pkgdir/usr/share/applications"
    sed -e 's|^Exec=.*|Exec=orcastudio %F|' \
        -e 's|^Icon=.*|Icon=orcastudio|' \
        squashfs-root/com.orcaslicer.OrcaStudio.desktop > "$pkgdir/usr/share/applications/orcastudio.desktop"
}
