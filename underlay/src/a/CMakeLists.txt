cmake_minimum_required(VERSION 3.12)

project(a VERSION 0.1.0 LANGUAGES C)

include(CMakePackageConfigHelpers)

set(LIB_INSTALL_DIR "lib" CACHE STRING "Where libs go")

configure_package_config_file(a-config.cmake.in
  ${CMAKE_CURRENT_BINARY_DIR}/a-config.cmake
  INSTALL_DESTINATION ${LIB_INSTALL_DIR}/a/cmake)

write_basic_package_version_file(
  ${CMAKE_CURRENT_BINARY_DIR}/a-config-version.cmake
  VERSION ${a_VERSION}
  COMPATIBILITY SameMajorVersion)

install(FILES ${CMAKE_CURRENT_BINARY_DIR}/a-config.cmake
              ${CMAKE_CURRENT_BINARY_DIR}/a-config-version.cmake
        DESTINATION ${LIB_INSTALL_DIR}/a/cmake)
