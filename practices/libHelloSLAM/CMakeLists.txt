# 声明要求的 cmake 最低版本
cmake_minimum_required( VERSION 2.8 )

# 声明一个 cmake 工程
project( HelloSLAM )

# 设置编译模式
set( CMAKE_BUILD_TYPE "Release" )

# 共享库
add_library( helloSLAM SHARED libHelloSLAM.cpp )

# install library
install(
    TARGETS     helloSLAM
    EXPORT      helloSLAMTargets
    ARCHIVE     DESTINATION         /usr/local/lib/helloSLAM
    LIBRARY     DESTINATION         /usr/local/lib/helloSLAM
    INCLUDES    DESTINATION         /usr/local/include/helloSLAM
)

install(
    FILES libHelloSLAM.h DESTINATION /usr/local/include/helloSLAM
)

install(
    EXPORT helloSLAMTargets
    FILE helloSLAMConfig.cmake
    DESTINATION /usr/local/lib/cmake/helloSLAM
)
