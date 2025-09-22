# CMAKE version
cmake_minimum_required(VERSION 3.16)


# project setting
project(rand-shell VERSION 0.1.0 LANGUAGES C)


# C version
set(CMAKE_C_STANDARD 11)
# C언어 버전 강제
set(CMAKE_C_STANDARD_REQUIRED ON)
# GNU 확장 같은거 비활성화
set(CMAKE_C_EXTENSIONS OFF)


# 실행 파일
add_executable(rand-shell
    src/main.c
)


# include 경로
target_include_directories(rand-shell PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)


# 컴파일 옵션
target_compile_options(rand-shell PRIVATE
    $<$<CONFIG:Debug>:-g>
    $<$<CONFIG:Release>:-O2>
)


# install 규칙
install(TARGETS rand-shell RUNTIME DESTINATION bin)
