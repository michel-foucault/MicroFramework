cmake_minimum_required (VERSION 2.8)
project (MicroFramework.Core)

add_definitions(-DBOOST_ALL_NO_LIB)
set(Boost_USE_STATIC_LIBS ON)

find_package(Boost REQUIRED COMPONENTS thread-mt signals-mt )

file(GLOB_RECURSE MicroFrameworkCoreSources "System/*.cpp" "System/*.h")

include_directories ( $(MicroFramework_SOURCE_DIR) )
include_directories ( ${Boost_INCLUDE_DIRS} )
include_directories ( ${pugixml_SOURCE_DIR}/src )

add_library ( MicroFramework.Core  ${MicroFrameworkCoreSources} )
