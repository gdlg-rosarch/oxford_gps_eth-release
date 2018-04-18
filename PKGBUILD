# Script generated with Bloom
pkgdesc="ROS - Ethernet interface to OxTS GPS receivers (NCOM packet structure)"
url='http://wiki.ros.org/oxford_gps_eth'

pkgname='ros-melodic-oxford-gps-eth'
pkgver='0.0.6_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-melodic-catkin'
'ros-melodic-geometry-msgs'
'ros-melodic-nav-msgs'
'ros-melodic-roscpp'
'ros-melodic-roslaunch'
'ros-melodic-sensor-msgs'
'ros-melodic-tf'
)

depends=('ros-melodic-geometry-msgs'
'ros-melodic-nav-msgs'
'ros-melodic-roscpp'
'ros-melodic-roslaunch'
'ros-melodic-sensor-msgs'
'ros-melodic-tf'
)

conflicts=()
replaces=()

_dir=oxford_gps_eth
source=()
md5sums=()

prepare() {
    cp -R $startdir/oxford_gps_eth $srcdir/oxford_gps_eth
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/melodic/setup.bash ] && source /opt/ros/melodic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/melodic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

