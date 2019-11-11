# Maintainer: Acidburn <acidburn.pt@gmail.com>

pkgname=manjarin-gtk-theme
pkgver=20191111
pkgrel=1
pkgdesc='Manjarin is a GTK-theme developed for the Manjaro-Gnome Edition'
arch=('x86_64' 'i686')
url='https://github.com/Acidburn0zzz/manjarin-gtk-theme.git'
license=('GPL')
depends=('libgdm' 'gdm' 'gcr' 'gjs' 'gtk3' 'mutter' 'gtk-engine-murrine' 
	 'gnome-theme-macos-mojave-meta' 'gtk-engines' 'gtk-theme-macos-mojave'
	 'gnome-shell-theme-macos-mojave' 'capitaine-cursors' 'mojave-ct-icon-theme'
	 'wlc' 'wayland' 'wayland-protocols' 'waylandpp' 'libva' 'libva-utils'
	 'gnome-shell>=3.34.1+5+g072a9a484-1' 'gnome-shell-extensions>=3.34.1-1'
	 'gnome-mojave-timed-wallpaper' 'polkit' 'polkit-gnome')
makedepends=('manjaro-gnome-vanilla' 'cmake' 'clang' 'llvm' 'llvm-libs' 'gcc' 'gcc-libs'
	     'meson' 'ninja' 'git' 'cvs' 'svn' 'subversion' 'bzr')
options=('!strip')
source=("${pkgname}.zip::${url}/archive/${_commit}.zip")
sha256sums=('3f1478d4c7872164534b165559b04ccb4a7f3add9a8f1acd4096d695b411373a')

pkgver() {
    date +%Y%m%d
}

build() {
    mv ${srcdir}/${pkgname}-${_commit} ${srcdir}/${pkgname}
    mkdir -p ${srcdir}/build
    cd ${srcdir}/build
    cmake ../${pkgname}
    make
}

package() {
    make -C build DESTDIR="${pkgdir}" install
}
