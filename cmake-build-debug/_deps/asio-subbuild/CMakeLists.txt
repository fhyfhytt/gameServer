# Distributed under the OSI-approved BSD 3-Clause License.  See accompanying
# file Copyright.txt or https://cmake.org/licensing for details.

cmake_minimum_required(VERSION 3.17.5)

# We name the project and the target for the ExternalProject_Add() call
# to something that will highlight to the user what we are working on if
# something goes wrong and an error message is produced.

project(asio-populate NONE)

include(ExternalProject)
ExternalProject_Add(asio-populate
                     "UPDATE_DISCONNECTED" "False" "GIT_REPOSITORY" "https://github.com/chriskohlhoff/asio.git" "GIT_TAG" "asio-1-18-0" "GIT_SHALLOW" "TRUE"
                    SOURCE_DIR          "C:/Users/Administrator/Desktop/gameserverlearn/gameServer/build/asio-asio-1-18-0-src"
                    BINARY_DIR          "C:/Users/Administrator/Desktop/gameserverlearn/gameServer/cmake-build-debug/_deps/asio-build"
                    CONFIGURE_COMMAND   ""
                    BUILD_COMMAND       ""
                    INSTALL_COMMAND     ""
                    TEST_COMMAND        ""
                    USES_TERMINAL_DOWNLOAD  YES
                    USES_TERMINAL_UPDATE    YES
)
