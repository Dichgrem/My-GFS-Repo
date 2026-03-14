# Maintainer: Dich <no-reply@github.com>

pkgname='gui-for-singbox'
_pkgname='GUI.for.SingBox'
pkgver='1.21.0'
pkgrel='1'
pkgdesc='GUI for SingBox'
arch=('x86_64')
license=('GPL3')
options=('!debug')
depends=(
  'glibc'
  'webkit2gtk-4.1'
  'jq'
  'curl'
)
url="https://github.com/GUI-for-Cores/${_pkgname}"
install="${pkgname}.install"

source=(
  "${pkgname}-${pkgver}.zip::https://github.com/GUI-for-Cores/${_pkgname}/releases/download/v${pkgver}/${_pkgname}-linux-amd64.zip"
  "${pkgname}.desktop"
  "https://raw.githubusercontent.com/GUI-for-Cores/${_pkgname}/main/build/appicon.png"
)
sha256sums=('SKIP'
  'SKIP'
  'SKIP')

package() {
  install -Dm755 "${_pkgname}" -t "${pkgdir}/opt/${pkgname}"
  install -Dm644 *.png "${pkgdir}/opt/${pkgname}/icon/${pkgname}.png"
  install -Dm644 *.desktop -t "${pkgdir}/usr/share/applications"
}
