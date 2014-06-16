include_directories(
  ../include
  ${CURL_INCLUDE_DIR}
  ${LIBWEBSOCKETS_INCLUDE_DIRS}
  ../lib/libsocketio/include
  ../lib/chck/json/
)

file(GLOB SOURCES *.c)

list(APPEND CMAKE_C_FLAGS "-Wall -Wextra -Wno-variadic-macros -Wno-long-long")

add_library(gamenode
    ${SOURCES}
)

target_link_libraries(gamenode websockets json libsocketio ${CURL_LIBRARIES})
