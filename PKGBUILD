pkgname=at-home-modifier-evdev-ahm
pkgver=2.10.6
pkgrel=1
pkgdesc="a replacemet for xf86-input-evdev-ahm for shift space"
arch=(x86_64)
license=('custom')
depends=('systemd-libs' 'mtdev' 'libevdev')
makedepends=('xorg-server-devel' 'X-ABI-XINPUT_VERSION=24.1' 'xorgproto')
conflicts=('xorg-server<1.19.0' 'X-ABI-XINPUT_VERSION<24.1' 'X-ABI-XINPUT_VERSION>=25')
options=('!makeflags')
groups=('xorg-drivers')
source=(https://gitlab.com/at-home-modifier/download/raw/master/source/ahm-2.10.6.tar.bz2)

sha512sums=('68418483fdb98544bb78a15bd7e48e83d3d89c9d025fd6a7e3506bfb1ad4ad3bc7793fd7ed3bc03a0933f80f100c95ad72ce1588e2a8a1e6d877526ed5ef09ff')

build() {

  cd ${pkgname}-${pkgver}
  autoreconf -i configure.ac
  ./configure --prefix=/usr
  make

}


package() {

  cd ${pkgname}-${pkgver}

  make DESTDIR="${pkgdir}" install

  install -m755 -d "${pkgdir}/usr/share/licenses/${pkgname}"

  install -m644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/"

}

