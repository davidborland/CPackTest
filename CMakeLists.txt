cmake_minimum_required(VERSION 3.0)

project(CPackTest)

add_executable(CPackTest MACOSX_BUNDLE CPackTest.cxx)
install(TARGETS CPackTest RUNTIME DESTINATION . BUNDLE DESTINATION .)

# CPack
if(WIN32)
	set(CPACK_GENERATOR NSIS)
elseif(APPLE)
	set(CPACK_GENERATOR DragNDrop)
endif()

set(CPACK_PACKAGE_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/Installer)
set(CPACK_PACKAGE_INSTALL_DIRECTORY "CPackTest")
set(CPACK_PACKAGE_EXECUTABLES CPackTest;CPackTest)

include(CPack)
