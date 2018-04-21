# Script generated with Bloom
pkgdesc="ROS - UWSim is an UnderWater SIMulator for marine robotics research and development. UWSim visualizes an underwater virtual scenario that can be configured using standard modeling software. Controllable underwater vehicles, surface vessels and robotic manipulators, as well as simulated sensors, can be added to the scene and accessed externally through ROS interfaces. This allows to easily integrate the visualization tool with existing control architectures."
url='http://www.irs.uji.es/uwsim/'

pkgname='ros-kinetic-uwsim'
pkgver='1.4.1_1'
pkgrel=1
arch=('any')
license=('GPL'
)

makedepends=('boost'
'libxml++'
'mesa'
'openscenegraph'
'ros-kinetic-catkin'
'ros-kinetic-geometry-msgs'
'ros-kinetic-image-transport'
'ros-kinetic-interactive-markers'
'ros-kinetic-kdl-parser'
'ros-kinetic-nav-msgs'
'ros-kinetic-osg-interactive-markers'
'ros-kinetic-osg-markers'
'ros-kinetic-osg-utils'
'ros-kinetic-pcl-ros'
'ros-kinetic-pluginlib'
'ros-kinetic-resource-retriever'
'ros-kinetic-robot-state-publisher'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-tf'
'ros-kinetic-underwater-sensor-msgs'
'ros-kinetic-urdf'
'ros-kinetic-uwsim-bullet'
'ros-kinetic-uwsim-osgbullet'
'ros-kinetic-uwsim-osgocean'
'ros-kinetic-uwsim-osgworks'
'ros-kinetic-xacro'
)

depends=('boost'
'libxml++'
'mesa'
'openscenegraph'
'ros-kinetic-geometry-msgs'
'ros-kinetic-image-transport'
'ros-kinetic-interactive-markers'
'ros-kinetic-kdl-parser'
'ros-kinetic-nav-msgs'
'ros-kinetic-osg-interactive-markers'
'ros-kinetic-osg-markers'
'ros-kinetic-osg-utils'
'ros-kinetic-pcl-ros'
'ros-kinetic-pluginlib'
'ros-kinetic-resource-retriever'
'ros-kinetic-robot-state-publisher'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-tf'
'ros-kinetic-underwater-sensor-msgs'
'ros-kinetic-urdf'
'ros-kinetic-uwsim-bullet'
'ros-kinetic-uwsim-osgbullet'
'ros-kinetic-uwsim-osgocean'
'ros-kinetic-uwsim-osgworks'
'ros-kinetic-xacro'
)

conflicts=()
replaces=()

_dir=uwsim
source=()
md5sums=()

prepare() {
    cp -R $startdir/uwsim $srcdir/uwsim
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

