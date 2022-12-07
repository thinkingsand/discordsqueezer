pkgname="discordsqueezer"
pkgver="1.0.0"
pkgrel="1"
pkgdesc="Video compression tool for Discord file size limits"
arch=("x86_64")
source=("git+https://github.com/mcharlsto/discordsqueezer.git"
        "git+https://github.com/kkroening/ffmpeg-python")
depends=("python" "python-pip" "python-pyqt5" "ffmpeg")
sha256sums=("SKIP" "SKIP")
makedepends=("git")

package() {
    cd ffmpeg-python
    /usr/bin/python setup.py install --root="$pkgdir/" --optimize=1
    mkdir -p "${pkgdir}/usr/bin"
    cd ..
    cp discordsqueezer/main.py ${pkgdir}/usr/bin/discordsqueezer
    cp discordsqueezer/discordsqueezer_ui.py ${pkgdir}/usr/bin/discordsqueezer_ui.py
    mkdir -p "${pkgdir}/usr/share/applications"
    cp discordsqueezer/DiscordSqueezer.desktop ${pkgdir}/usr/share/applications/DiscordSqueezer.desktop
    chmod +x "${pkgdir}/usr/bin/discordsqueezer"
    mkdir -p "${pkgdir}/usr/share/icons/hicolor/512x512/apps"
    cp discordsqueezer/icon/discordsqueezer.png ${pkgdir}/usr/share/icons/hicolor/512x512/apps/discordsqueezer.png
}
