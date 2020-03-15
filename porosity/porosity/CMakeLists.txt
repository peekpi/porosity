cmake_minimum_required( VERSION 3.0 )
project (Porosity)
set(CMAKE_CXX_STANDARD 14)

find_package(Boost REQUIRED COMPONENTS
# regex
filesystem   # 我的工程中只使用了 boost 的 filesystem 功能,因此这里只有一个组件
)
if(NOT Boost_FOUND)
    message("Not found Boost")
endif()


include_directories(${Boost_INCLUDE_DIRS})

message("${Boost_INCLUDE_DIRS}")
message("${Boost_LIBRARIES}")

file(GLOB sources "*.cpp")
file(GLOB headers "*.h")

add_executable(porosity ${sources} ${headers})

