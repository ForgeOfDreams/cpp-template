project(VERSION 3.31)

#=============================
# Project / Package metadata
#=============================

set(BREAD_PACKAGE_NAME "project")
set(BREAD_PROJECT_VERSION_MAJOR 0)
set(BREAD_PROJECT_VERSION_MINOR 0)
set(BREAD_PROJECT_VERSION_BUILD 1)
set(BREAD_PROJECT_DESCRIPTION "")

project(BreadProject
    VERSION ${BREAD_PROJECT_VERSION_MAJOR}.${BREAD_PROJECT_VERSION_MINOR}.${BREAD_PROJECT_VERSION_BUILD}
    DESCRIPTION BREAD_PROJECT_DESCRIPTION
    LANGUAGES CXX C
)

set(BREAD_PROJECT_VERSION_STRING ${PROJECT_VERSION})

#=============================
# Language setup
#=============================

enable_language(CXX)
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

#=============================
# Configurable options
#=============================

include(CMakeDependentOption)
include(GNUInstallDirs)

string(COMPARE EQUAL ${CMAKE_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR} PROJECT_IS_TOP_LEVEL)

option(BREAD_PROJECT_BUILD "Build." OFF)
option(BREAD_PROJECT_BUILD_TESTS "Tests." OFF)
option(BREAD_PROJECT_BUILD_EXAMPLES "Examples." OFF)
option(BREAD_PROJECT_INSTALL "Install." ${PROJECT_IS_TOP_LEVEL})

if(NOT DEFINED CMAKE_BUILD_TYPE AND NOT DEFINED CMAKE_CONFIGURATION_TYPES)
    set(CMAKE_BUILD_TYPE Release CACHE STRING "Build type" FORCE)
    set_property(CACHE CMAKE_BUILD_TYPE PROPERTY STRINGS "Debug" "Release" "MinSizeRel" "RelWithDebInfo")
endif()

list(APPEND CMAKE_MODULE_PATH 
    ${PROJECT_SOURCE_DIR}/cmake/modules
#    ${PROJECT_SOURCE_DIR}/cmake/modules/cm-src-collector
)

set(CMAKE_CXX_VISIBILITY_PRESET hidden)
set(CMAKE_VISIBILITY_INLINES_HIDDEN ON)

add_library(BreadProject)
add_library(Bread::Project ALIAS BreadProject)

#=============================
# Modules
#=============================

# include(СSrcCollector)

#=============================
# Subdirectory
#=============================

if (BREAD_PROJECT_BUILD)
    add_subdirectory(src)
endif()

#=============================
# Test
#=============================

if(BREAD_PROJECT_BUILD AND BREAD_PROJECT_BUILD_TESTS)    
    add_subdirectory(tests)
endif()

#=============================
# Examples
#=============================

if(BREAD_PROJECT_BUILD AND BREAD_PROJECT_BUILD_EXAMPLES)
    add_subdirectory(examples)
endif()
