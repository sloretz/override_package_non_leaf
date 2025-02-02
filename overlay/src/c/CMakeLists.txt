cmake_minimum_required(VERSION 3.12)

project(c VERSION 0.1.0 LANGUAGES C)

find_package(a REQUIRED)

include(CMakePackageConfigHelpers)

set(LIB_INSTALL_DIR "lib" CACHE STRING "Where libs go")

configure_package_config_file(c-config.cmake.in
  ${CMAKE_CURRENT_BINARY_DIR}/c-config.cmake
  INSTALL_DESTINATION ${LIB_INSTALL_DIR}/c/cmake)

write_basic_package_version_file(
  ${CMAKE_CURRENT_BINARY_DIR}/c-config-version.cmake
  VERSION ${b_VERSION}
  COMPATIBILITY SameMajorVersion)

install(FILES ${CMAKE_CURRENT_BINARY_DIR}/c-config.cmake
              ${CMAKE_CURRENT_BINARY_DIR}/c-config-version.cmake
        DESTINATION ${LIB_INSTALL_DIR}/c/cmake)
