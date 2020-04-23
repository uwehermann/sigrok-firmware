##
## This file is part of the sigrok-firmware project.
##
## Copyright (C) 2020 Uwe Hermann <uwe@hermann-uwe.de>
##
## This program is free software: you can redistribute it and/or modify
## it under the terms of the GNU General Public License as published by
## the Free Software Foundation, either version 2 of the License, or
## (at your option) any later version.
##
## This program is distributed in the hope that it will be useful,
## but WITHOUT ANY WARRANTY; without even the implied warranty of
## MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
## GNU General Public License for more details.
##
## You should have received a copy of the GNU General Public License
## along with this program.  If not, see <http://www.gnu.org/licenses/>.
##

cmake_minimum_required(VERSION 3.12)

project(sigrok-firmware VERSION 0.1.0 LANGUAGES C)

include(GNUInstallDirs)

set(D "${CMAKE_INSTALL_DATAROOTDIR}/sigrok-firmware")
install(DIRECTORY asix-sigma/ DESTINATION ${D} PATTERN "LICENSE*" EXCLUDE)
install(DIRECTORY sysclk-lwla/ DESTINATION ${D} PATTERN "LICENSE*" EXCLUDE)

message(STATUS "CMake: ${CMAKE_COMMAND} ${CMAKE_VERSION}")

set(CPACK_SOURCE_PACKAGE_FILE_NAME "${PROJECT_NAME}-${PROJECT_VERSION}")
set(CPACK_SOURCE_IGNORE_FILES ${CMAKE_CURRENT_BINARY_DIR} ".git*")
set(CPACK_SOURCE_GENERATOR "TGZ")
include(CPack)
