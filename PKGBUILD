# Script generated with Bloom
pkgdesc="ROS - RTAB-Map's ros-pkg. RTAB-Map is a RGB-D SLAM approach with real-time constraints."


pkgname='ros-kinetic-rtabmap-ros'
pkgver='0.11.13_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('pcl'
'ros-kinetic-catkin'
'ros-kinetic-class-loader'
'ros-kinetic-costmap-2d'
'ros-kinetic-cv-bridge'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-eigen-conversions'
'ros-kinetic-genmsg'
'ros-kinetic-geometry-msgs'
'ros-kinetic-image-geometry'
'ros-kinetic-image-transport'
'ros-kinetic-laser-geometry'
'ros-kinetic-message-filters'
'ros-kinetic-move-base-msgs'
'ros-kinetic-nav-msgs'
'ros-kinetic-nodelet'
'ros-kinetic-octomap-ros'
'ros-kinetic-pcl-conversions'
'ros-kinetic-pcl-ros'
'ros-kinetic-roscpp'
'ros-kinetic-rospy'
'ros-kinetic-rtabmap'
'ros-kinetic-rviz'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-stereo-msgs'
'ros-kinetic-tf'
'ros-kinetic-tf-conversions'
'ros-kinetic-tf2-ros'
'ros-kinetic-visualization-msgs'
)

depends=('ros-kinetic-class-loader'
'ros-kinetic-costmap-2d'
'ros-kinetic-cv-bridge'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-eigen-conversions'
'ros-kinetic-geometry-msgs'
'ros-kinetic-image-geometry'
'ros-kinetic-image-transport'
'ros-kinetic-image-transport-plugins'
'ros-kinetic-laser-geometry'
'ros-kinetic-message-filters'
'ros-kinetic-move-base-msgs'
'ros-kinetic-nav-msgs'
'ros-kinetic-nodelet'
'ros-kinetic-octomap-ros'
'ros-kinetic-pcl-conversions'
'ros-kinetic-pcl-ros'
'ros-kinetic-roscpp'
'ros-kinetic-rospy'
'ros-kinetic-rtabmap'
'ros-kinetic-rviz'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-stereo-msgs'
'ros-kinetic-tf'
'ros-kinetic-tf-conversions'
'ros-kinetic-tf2-ros'
'ros-kinetic-visualization-msgs'
)

conflicts=()
replaces=()

_dir=rtabmap_ros
source=()
md5sums=()

prepare() {
    cp -R $startdir/rtabmap_ros $srcdir/rtabmap_ros
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

