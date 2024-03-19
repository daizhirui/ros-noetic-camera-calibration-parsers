# Script generated with import_catkin_packages.py.
# For more information: https://github.com/bchretien/arch-ros-stacks.
pkgdesc="ROS - camera_calibration_parsers contains routines for reading and writing camera calibration parameters."
url='https://wiki.ros.org/camera_calibration_parsers'

pkgname='ros-noetic-camera-calibration-parsers'
pkgver='1.12.0'
arch=('i686' 'x86_64' 'aarch64' 'armv7h' 'armv6h')
pkgrel=2
license=('BSD')

ros_makedepends=(
	ros-noetic-catkin
	ros-noetic-rosconsole
	ros-noetic-roscpp
	ros-noetic-roscpp-serialization
	ros-noetic-sensor-msgs
)

makedepends=(
	'cmake'
	'ros-build-tools'
	${ros_makedepends[@]}
	yaml-cpp
	boost
	pkg-config
)

ros_depends=(
	ros-noetic-sensor-msgs
	ros-noetic-roscpp
	ros-noetic-roscpp-serialization
)

depends=(
	${ros_depends[@]}
	boost
	yaml-cpp
)

_commit="21aac6a4b84017c10e8ed7ad86bc59826a77aa1f"
_dir="image_common-${_commit}/camera_calibration_parsers"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros-perception/image_common/archive/${_commit}.tar.gz")
sha256sums=('b367ef2bac0222a747c5dac760055a80b3569b408021522afe61c15e19e2c246')

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
