##############################################################################
# Cmake
##############################################################################

cmake_minimum_required(VERSION 3.5)
project(ecl_devices)

##############################################################################
# Find Packages
##############################################################################

find_package(ament_cmake_ros REQUIRED)
find_package(ecl_build REQUIRED)
find_package(ecl_config REQUIRED)
find_package(ecl_containers REQUIRED)
find_package(ecl_errors REQUIRED)
find_package(ecl_mpl REQUIRED)
find_package(ecl_threads REQUIRED)
find_package(ecl_type_traits REQUIRED)
find_package(ecl_utilities REQUIRED)

##############################################################################
# Project Configuration
##############################################################################

ament_package_xml()
ecl_enable_cxx14_compiler()

##############################################################################
# Sources
##############################################################################

add_subdirectory(include)
add_subdirectory(src)

##############################################################################
# Exports
##############################################################################

ament_export_interfaces(${PROJECT_NAME})
ament_export_dependencies(
    ecl_config
    ecl_containers
    ecl_errors
    ecl_mpl
    ecl_threads
    ecl_type_traits
    ecl_utilities
)
ament_package()
