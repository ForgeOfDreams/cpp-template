include(GenerateExportHeader)
include(CMakePackageConfigHelpers)

#=============================
# Config
#=============================

# write_basic_package_version_file(
#     ${PROJECT_BINARY_DIR}/bproject-version.cmake
#     VERSION ${PROJECT_VERSION}
#     COMPATIBILITY AnyNewerVersion
# )

# configure_file(
#     ${PROJECT_SOURCE_DIR}/cmake/bproject-build-config.h.in
#     ${PROJECT_BINARY_DIR}/include/bproject-build-config.h
# )

#=============================
# Sources
#=============================



#=============================
# Install
#=============================

if (BREAD_PROJECT_BUILD AND BREAD_PROJECT_INSTALL AND NOT CMAKE_SKIP_INSTALL_RULES)

endif()