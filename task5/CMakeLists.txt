cmake_minimum_required (VERSION 3.0)
project(driver_cmakeproject)
set (CMAKE_CXX_STANDARD 11)

include_directories(${CMAKE_SOURCE_DIR}/include)
link_directories(${CMAKE_SOURCE_DIR}/lib)

set(SOURCES src/driver.c)
add_executable(myapp ${PROJECT_SOURCE_DIR}/${SOURCES})

target_link_libraries(myapp libmyfunctions.so libmyfunctions.a)

install(TARGETS myapp DESTINATION /usr/bin)
install(FILES man/addBitwise.3 DESTINATION /usr/share/man/man3)


include(InstallRequiredSystemLibraries)
set(CPACK_GENERATOR "DEB")
set(CPACK_DEBIAN_PACKAGE_MAINTAINER "Jawayria")
include(CPack)
