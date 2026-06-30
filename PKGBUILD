# Maintainer: Dich <no-reply@github.com>

pkgname='gui-for-singbox'
_pkgname='GUI.for.SingBox'
pkgver=1.25.4
pkgrel=1
pkgdesc='GUI for SingBox'
arch=('x86_64')
license=('GPL-3.0-only')
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
sha256sums=('cf2367cb5203c583b4683187cde597e5bd7f9f2e55b08f9f2ba98c422c5bb793'
            '576a9561c73fdc39f31670ac5cb6fefc61822a348f116f0d64f9e2e402882729'
            '08257d0d21c76a56e48e38105460927293a452ddc6b0b62db401bf5b5b9b7adf')

package() {
  install -Dm755 "${_pkgname}" -t "${pkgdir}/opt/${pkgname}"
  install -Dm644 *.png "${pkgdir}/opt/${pkgname}/icon/${pkgname}.png"
  install -Dm644 *.desktop -t "${pkgdir}/usr/share/applications"
}
