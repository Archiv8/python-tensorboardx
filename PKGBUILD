#!/bin/bash

# Based on the orginal packaging by Martino Pilia <martino.pilia@gmail.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# [ToDo]: Add files: User documentation
# [ToDo]: Add files: Tooling
# [FixMe]: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/orgs/Archiv8/python-tensorboardx/discussions>
# Contributor: Ross Clark <https://github.com/orgs/Archiv8/fpython-tensorboardx/discussions>

_langname=python
_relname=tensorboardx

pkgname="${_langname}-${_relname}"
pkgver=2.5
pkgrel=1
pkgdesc="Tensorboard for PyTorch"
arch=(
  "any"
)
url="https://github.com/lanpa/tensorboardX"
license=(
  "MIT"
)
depends=(
  # Arch Linux Official Repositories
  "python-numpy"
  "python-protobuf"
  "python-pytorch"

  # Archiv8 / AUR
  "python-soundfile"
)
makedepends=(
  # Arch Linux Official Repositories
  "python-setuptools"
  "git"
)
checkdepends=(
  # Arch Linux Official Repositories
  "python-future"
  "python-pytest"
  "python-matplotlib"

  # Archiv8 / AUR
  "python-crc32c"
)
conflicts=(
  "python-tensorboard-git"
)
source+=(
  "https://files.pythonhosted.org/packages/source/${_relname::1}/$_relname/$_relname-$pkgver.tar.gz"
)
sha512sums=(
  "54075b10dc61d9bf4730f4b723c33ecb11c1089cb9534cec9e53d5c14b8bc54d0dc93c2634ff955bb54a3acf41d2591c54fe92f05ebd24a71cf916d9e1867d71"
)

package() {
  cd "${srcdir}/${_relname}-${pkgver}"

  install -D -m644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"

  python setup.py install --optimize=1 --root="${pkgdir}"
}
