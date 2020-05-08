cmake_minimum_required(VERSION 3.0)

project(CPackTest)

add_executable(CPackTest CPackTest.cxx)
install(TARGETS CPackTest RUNTIME)

# CPack
set(CPACK_GENERATOR NSIS)
set(CPACK_PACKAGE_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/Installer)
set(CPACK_PACKAGE_INSTALL_DIRECTORY "CPackTest")
set(CPACK_PACKAGE_EXECUTABLES CPackTest;CPackTest)

include(CPack)