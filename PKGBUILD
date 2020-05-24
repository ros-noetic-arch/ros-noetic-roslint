# Script generated with import_catkin_packages.py.
# For more information: https://github.com/bchretien/arch-ros-stacks.
pkgdesc="ROS - CMake lint commands for ROS packages."
url='https://wiki.ros.org/roslint'

pkgname='ros-noetic-roslint'
pkgver='0.11.2'
_pkgver_patch=0
arch=('any')
pkgrel=2
license=('BSD')

ros_makedepends=(
	ros-noetic-catkin
)

makedepends=(
	'cmake'
	'ros-build-tools'
	${ros_makedepends[@]}
)

ros_depends=(
)

depends=(
	${ros_depends[@]}
)

_dir="roslint-${pkgver}"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros/roslint/archive/${pkgver}.tar.gz")
sha256sums=('e86b12ddf03cf1530b3343df797e381bcb8214004c992b7ac280918fd70672f0')

build() {
	# Use ROS environment variables.
	source /usr/share/ros-build-tools/clear-ros-env.sh
	[ -f /opt/ros/noetic/setup.bash ] && source /opt/ros/noetic/setup.bash

	# Create the build directory.
	[ -d ${srcdir}/build ] || mkdir ${srcdir}/build
	cd ${srcdir}/build

	# Build the project.
	cmake ${srcdir}/${_dir} \
		-DCATKIN_BUILD_BINARY_PACKAGE=ON \
		-DCMAKE_INSTALL_PREFIX=/opt/ros/noetic \
		-DPYTHON_EXECUTABLE=/usr/bin/python \
		-DSETUPTOOLS_DEB_LAYOUT=OFF
	make
}

package() {
	cd "${srcdir}/build"
	make DESTDIR="${pkgdir}/" install
}
