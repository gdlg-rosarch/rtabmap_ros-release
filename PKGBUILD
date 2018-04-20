# Script generated with Bloom
pkgdesc="ROS - RTAB-Map's ros-pkg. RTAB-Map is a RGB-D SLAM approach with real-time constraints."


pkgname='ros-lunar-rtabmap-ros'
pkgver='0.13.2_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('pcl'
'ros-lunar-catkin'
'ros-lunar-class-loader'
'ros-lunar-costmap-2d'
'ros-lunar-cv-bridge'
'ros-lunar-dynamic-reconfigure'
'ros-lunar-eigen-conversions'
'ros-lunar-genmsg'
'ros-lunar-geometry-msgs'
'ros-lunar-image-geometry'
'ros-lunar-image-transport'
'ros-lunar-laser-geometry'
'ros-lunar-message-filters'
'ros-lunar-move-base-msgs'
'ros-lunar-nav-msgs'
'ros-lunar-nodelet'
'ros-lunar-octomap-ros'
'ros-lunar-pcl-conversions'
'ros-lunar-pcl-ros'
'ros-lunar-roscpp'
'ros-lunar-rospy'
'ros-lunar-rtabmap'
'ros-lunar-rviz'
'ros-lunar-sensor-msgs'
'ros-lunar-std-msgs'
'ros-lunar-std-srvs'
'ros-lunar-stereo-msgs'
'ros-lunar-tf'
'ros-lunar-tf-conversions'
'ros-lunar-tf2-ros'
'ros-lunar-visualization-msgs'
)

depends=('ros-lunar-class-loader'
'ros-lunar-compressed-depth-image-transport'
'ros-lunar-compressed-image-transport'
'ros-lunar-costmap-2d'
'ros-lunar-cv-bridge'
'ros-lunar-dynamic-reconfigure'
'ros-lunar-eigen-conversions'
'ros-lunar-geometry-msgs'
'ros-lunar-image-geometry'
'ros-lunar-image-transport'
'ros-lunar-laser-geometry'
'ros-lunar-message-filters'
'ros-lunar-move-base-msgs'
'ros-lunar-nav-msgs'
'ros-lunar-nodelet'
'ros-lunar-octomap-ros'
'ros-lunar-pcl-conversions'
'ros-lunar-pcl-ros'
'ros-lunar-roscpp'
'ros-lunar-rospy'
'ros-lunar-rtabmap'
'ros-lunar-rviz'
'ros-lunar-sensor-msgs'
'ros-lunar-std-msgs'
'ros-lunar-std-srvs'
'ros-lunar-stereo-msgs'
'ros-lunar-tf'
'ros-lunar-tf-conversions'
'ros-lunar-tf2-ros'
'ros-lunar-visualization-msgs'
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
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
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

