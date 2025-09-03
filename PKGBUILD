pkgname=python-psutil
pkgver=7.0.0
pkgrel=1
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
sha256sums=(a3c736187215d1f94ebe18ee6b14202d1b89c165c2eaad159f55cdfb494f7a1c)

build() {
    cd ${pkgname#*-}-release-${pkgver}

    python3 -m build --wheel --no-isolation
}

package() {
    cd ${pkgname#*-}-release-${pkgver}

    python3 -m installer -d ${pkgdir} dist/*.whl
}
