set(ASIO_CMAKE_ASIO_TAG asio-1-18-0)
set(ASIO_CMAKE_ASIO_SOURCE_DIR ${PROJECT_SOURCE_DIR}/build)
set(ASIO_CMAKE_ASIO_DEP_DIR "${ASIO_CMAKE_ASIO_SOURCE_DIR}/asio-${ASIO_CMAKE_ASIO_TAG}-src")

include(FetchContent)
FetchContent_Declare(asio
  GIT_REPOSITORY  https://github.com/chriskohlhoff/asio.git
  GIT_TAG         ${ASIO_CMAKE_ASIO_TAG}
  GIT_SHALLOW     TRUE  # shallow clone
  SOURCE_DIR      ${ASIO_CMAKE_ASIO_DEP_DIR}
)
FetchContent_MakeAvailable(asio)
add_library(asio INTERFACE)
target_include_directories(asio INTERFACE ${asio_SOURCE_DIR}/asio/include)
target_compile_definitions(asio INTERFACE
    ASIO_STANDALONE     # don't use Boost
    ASIO_NO_DEPRECATED
)
add_subdirectory(spdlog)