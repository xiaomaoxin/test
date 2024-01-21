# 设置 C 标准
set(CMAKE_C_STANDARD 11)

# 设置 CMake 最低版本要求
cmake_minimum_required(VERSION 3.22)

project(test1 VERSION 1.0.0 LANGUAGES C)
# 指定头文件目录
include_directories(inc)

## 查找 pthread 库
#find_package(Threads REQUIRED)

# 添加C源文件
set(C_SOURCE_FILES
        src/main.c
        src/person.c
)

# 创建可执行文件
add_executable(${PROJECT_NAME} ${C_SOURCE_FILES})
# 设置链接器脚本
target_include_directories(${PROJECT_NAME}  PRIVATE  ${PROJECT_SOURCE_DIR}/inc)

#target_link_libraries(${PROJECT_NAME} PRIVATE Threads::Threads)