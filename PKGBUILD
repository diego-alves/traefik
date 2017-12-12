# Maintainer: Diego Alves <dalves@gmail.com>

pkgname="traefik"
pkgver=1.4.5
pkgrel=1
pkgdesc='A modern reverse proxy'
arch=('x86_64')
url='https://github.com/containous/traefik'
license=('MIT')
install="${pkgname}.install"
backup=(
  'etc/traefik/traefik.toml'
)
source=(
  "traefik.service"
  "traefik.toml"
  "https://github.com/containous/${pkgname}/releases/download/v${pkgver}/${pkgname}"
)
sha512sums=('0872198f6bc7fbd56eaba9611573a0e426bac95e449564cf117260515f6827222de0b7228683b995dfbd93eb46c881421db20c1c6bd7cd619800be7b525f63af'
            'af51c55a6954c9fd084da681b89656f896dd66834fa2230f261a2a829265b8aaddebbf59cf2b514b46c845901e33196ba273a8b0ee60cff1a7ab568baa5d15f4'
            '8eb73b36f94b2c311b17b2632c3f9540af12d2e9d08f08f90ce9fbc405c6c7a541687958ceb580686ad15a504ecf768f3f82984777180366edc22fcaf2dc9078')
package() {
  install -d -m755 "${pkgdir}/var/log/traefik"
  install -D -m644 "${srcdir}/traefik.service" "${pkgdir}/usr/lib/systemd/system/traefik.service"
  install -D -m644 "${srcdir}/traefik.toml" "${pkgdir}/etc/traefik/traefik.toml"
  install -D -m755 "${srcdir}/${pkgname}" "${pkgdir}/usr/bin/${pkgname}"
}