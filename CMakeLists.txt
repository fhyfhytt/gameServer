cmake_minimum_required(VERSION 3.17)
project(gameServer)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(src_file
        ${CMAKE_CURRENT_SOURCE_DIR}/src/main.cpp
        )
add_subdirectory(lib)

add_executable(gameServer ${src_file})
# 编译子文件夹的CMakeLists.txt

# 将.cpp/.c/.cc文件生成.a静态库
# 注意，库文件名称通常为libxxx.so，在这里只要写xxx即可
#add_library(库文件名称 STATIC 文件)

# 将.cpp/.c/.cc文件生成可执行文件
#add_executable(可执行文件名称 文件)

# 规定.h头文件路径
#include_directories(路径)

# 规定.so/.a库文件路径
#link_directories(路径)
# 对add_library或add_executable生成的文件进行链接操作
# 注意，库文件名称通常为libxxx.so，在这里只要写xxx即可
#target_link_libraries(库文件名称/可执行文件名称 链接的库文件名称)
#add_subdirectory必须进行link
target_link_libraries(gameServer PRIVATE spdlog::spdlog)
target_link_libraries(gameServer PRIVATE asio)

## 指定头文件路径
#target_include_directories(gameServer PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include/)
## 指定lib文件路径
#target_link_libraries(gameServer PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include/)