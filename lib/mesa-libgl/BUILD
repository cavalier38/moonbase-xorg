prepare_install  &&

# Find the mesa libGL
LINK_TARGET=$(readlink -f /usr/lib/mesa/libGL.so)  &&
# Make path relative
LINK_TARGET=${LINK_TARGET#/usr/lib/}  &&

# Find version of mesa lib
TARGET_VERSION=${LINK_TARGET##*.so}  &&

while [ -n "$TARGET_VERSION" ] ; do
  ln -sf $LINK_TARGET /usr/lib/libGL.so$TARGET_VERSION
  TARGET_VERSION=${TARGET_VERSION%.*}
done  &&

ln -sf $LINK_TARGET /usr/lib/libGL.so

