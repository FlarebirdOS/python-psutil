pkgname=python-psutil
pkgver=7.1.1
pkgrel=2
pkgdesc="A cross-platform process and system utilities module for Python"
arch=('x86_64')
url="https://github.com/giampaolo/psutil"
license=('BSD-3-Clause')
depends=('python')
makedepends=(
    'python-build'
    'python-installer'
    'python-setuptools'
    'python-wheel'
)
source=(https://github.com/giampaolo/psutil/archive/release-${pkgver}/${pkgname#*-}-release-${pkgver}.tar.gz)
sha256sums=(ace52509be7b62d25b88d1eb2db997898b74c79fdecbaadab304bbd4a54e2068)

build() {
    cd ${pkgname#*-}-release-${pkgver}

    python3 -m build --wheel --no-isolation
}

package() {
    cd ${pkgname#*-}-release-${pkgver}

    python3 -m installer -d ${pkgdir} dist/*.whl
}
