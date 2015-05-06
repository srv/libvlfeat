cmake_minimum_required(VERSION 2.8.3)
project(libvlfeat)

find_package(catkin REQUIRED)

catkin_package(
 INCLUDE_DIRS vlfeat/vl
 LIBRARIES vlfeat
)

include_directories(vlfeat/vl)

set(CMAKE_C_FLAGS "-mavx")

add_library(vlfeat
  vlfeat/vl/aib.c
  vlfeat/vl/array.c
  vlfeat/vl/covdet.c
  vlfeat/vl/dsift.c
  vlfeat/vl/fisher.c
  vlfeat/vl/generic.c
  vlfeat/vl/getopt_long.c
  vlfeat/vl/gmm.c
  vlfeat/vl/hikmeans.c
  vlfeat/vl/hog.c
  vlfeat/vl/homkermap.c
  vlfeat/vl/host.c
  vlfeat/vl/ikmeans.c
  vlfeat/vl/imopv.c
  vlfeat/vl/imopv_sse2.c
  vlfeat/vl/kdtree.c
  vlfeat/vl/kmeans.c
  vlfeat/vl/lbp.c
  vlfeat/vl/liop.c
  vlfeat/vl/mathop_avx.c
  vlfeat/vl/mathop.c
  vlfeat/vl/mathop_sse2.c
  vlfeat/vl/mser.c
  vlfeat/vl/pgm.c
  vlfeat/vl/quickshift.c
  vlfeat/vl/random.c
  vlfeat/vl/rodrigues.c
  vlfeat/vl/scalespace.c
  vlfeat/vl/sift.c
  vlfeat/vl/slic.c
  vlfeat/vl/stringop.c
  vlfeat/vl/svm.c
  vlfeat/vl/svmdataset.c
  vlfeat/vl/vlad.c
  vlfeat/vl/ikmeans_elkan.tc
  vlfeat/vl/ikmeans_init.tc
  vlfeat/vl/ikmeans_lloyd.tc
)

install(TARGETS vlfeat
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

install(DIRECTORY vlfeat/vl
  DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
  FILES_MATCHING PATTERN "*.h"
  PATTERN ".svn" EXCLUDE
)
