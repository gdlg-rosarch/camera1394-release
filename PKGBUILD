# Script generated with Bloom
pkgdesc="ROS - ROS driver for devices supporting the IEEE 1394 Digital Camera (IIDC) protocol. Supports the ROS image_pipeline, using libdc1394 for device access."
url='http://ros.org/wiki/camera1394'

pkgname='ros-kinetic-camera1394'
pkgver='1.10.1_1'
pkgrel=1
arch=('any')
license=('LGPL'
)

makedepends=('boost'
'libdc1394'
'ros-kinetic-camera-info-manager'
'ros-kinetic-catkin'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-image-transport'
'ros-kinetic-message-generation'
'ros-kinetic-nodelet'
'ros-kinetic-roscpp'
'ros-kinetic-rostest'
'ros-kinetic-sensor-msgs'
'ros-kinetic-tf'
)

depends=('boost'
'libdc1394'
'ros-kinetic-camera-info-manager'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-image-transport'
'ros-kinetic-message-runtime'
'ros-kinetic-nodelet'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-tf'
)

conflicts=()
replaces=()

_dir=camera1394
source=()
md5sums=()

prepare() {
    cp -R $startdir/camera1394 $srcdir/camera1394
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
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

