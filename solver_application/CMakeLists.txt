cmake_minimum_required(VERSION 3.10)
project(solver)

# creating an executable from source
add_executable(solver ${CMAKE_CURRENT_SOURCE_DIR}/equation.cpp)

# linking with formatter_ex and solver_lib
target_link_libraries(solver PRIVATE formatter_ex solver_lib)

include(InstallRequiredSystemLibraries)

set(CPACK_PACKAGE_NAME "solver")
set(CPACK_PACKAGE_VENDOR "dp apps")
set(CPACK_PACKAGE_CONTACT ${GITHUB_EMAIL})
set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "solver app for quadratic equations")
set(CPACK_PACKAGE_VERSION_MAJOR "1")
set(CPACK_PACKAGE_VERSION_MINOR "0")
set(CPACK_PACKAGE_VERSION_PATCH "0")

set(CPACK_GENERATOR "ZIP;TGZ")

