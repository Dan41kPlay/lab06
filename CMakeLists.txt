cmake_minimum_required(VERSION 3.10)
project(lab06)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(formatter_lib)
add_subdirectory(formatter_ex_lib)
add_subdirectory(solver_lib)
add_subdirectory(hello_world_application)
add_subdirectory(solver_application)

install(TARGETS formatter formatter_ex solver_lib
	ARCHIVE DESTINATION lib
	LIBRARY DESTINATION lib
	RUNTIME DESTINATION bin)
install(TARGETS solver
	RUNTIME DESTINATION bin)
install(DIRECTORY formatter_lib/ formatter_ex_lib/ solver_lib/
	DESTINATION include
	FILES_MATCHING PATTERN "*.h")

include(InstallRequiredSystemLibraries)

set(CPACK_PACKAGE_NAME "solver")
set(CPACK_PACKAGE_VENDOR "dp apps")
set(CPACK_PACKAGE_CONTACT ${GITHUB_EMAIL})
set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "solver app for quadratic equations")
set(CPACK_PACKAGE_VERSION_MAJOR "1")
set(CPACK_PACKAGE_VERSION_MINOR "0")
set(CPACK_PACKAGE_VERSION_PATCH "0")

set(CPACK_GENERATOR "ZIP;TGZ")

set(CPACK_DEBIAN_PACKAGE_MAINTAINER "dp229")
set(CPACK_DEBIAN_PACKAGE_DEPENDS "libc6 (>= 2.43)")


include(CPack)
