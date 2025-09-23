#...............................................................................
#
#  This file is part of the ECCKey utility.
#
#  ECCKey is distributed under the MIT license.
#  For details see accompanying license.txt file,
#  the public copy of which is also available at:
#  http://tibbo.com/downloads/archive/ecckey/license.txt
#
#...............................................................................

cmake_minimum_required(VERSION 3.16)

project (ecckey_b)

include (axl/cmake/axl_cmake.cmake NO_POLICY_SCOPE)

set(BUILD_AXL_TESTS OFF CACHE BOOL "AXL tests disabled" FORCE)
add_subdirectory (axl EXCLUDE_FROM_ALL)
include (axl/cmake/import_axl.cmake)

if(GCC_LINK_GLIBC_WRAPPERS)
	# force build axl_glibc
	# we link to axl_glibc using CMAKE_STANDARD_LIBRARIES; as such,
	# axl_glibc is not a direct dependency and will be skipped otherwise

	add_custom_target(
		force_build_axl_glibc ALL
		DEPENDS
			axl_glibc_libc
			axl_glibc_libm
	)
endif()

add_subdirectory (ecckey)

#...............................................................................
