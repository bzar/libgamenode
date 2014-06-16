CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
project(gamenode)

SET(LWS_WITHOUT_TESTAPPS ON CACHE BOOL "Don't build tests for libwebsockets")
SET(LWS_WITHOUT_DAEMONIZE ON CACHE BOOL "Don't build daemonize for libwebsockets")

set(gamenode_INCLUDE_DIRS ${gamenode_SOURCE_DIR}/include ${gamenode_SOURCE_DIR}/lib/chck/json/ CACHE PATH "Gamenode include dirs")

include_directories(
  ${gamenode_INCLUDE_DIRS}
)

find_package(CURL REQUIRED)

add_subdirectory(lib)
add_subdirectory(src)

