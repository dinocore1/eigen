cmake_minimum_required(VERSION 3.2 FATAL_ERROR)

project(eigen LANGUAGES CXX)

add_library(eigen
  INTERFACE
)


#target_compile_features(eigen
#	INTERFACE
#		cxx_variadic_templates
#)

target_include_directories(eigen
  INTERFACE $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
	$<INSTALL_INTERFACE:include>
)

install(TARGETS eigen
  EXPORT eigenConfig
)

install(DIRECTORY Eigen
  DESTINATION include
)

install(EXPORT eigenConfig
  DESTINATION cmake
)
