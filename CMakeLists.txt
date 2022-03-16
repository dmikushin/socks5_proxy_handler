cmake_minimum_required(VERSION 3.10)

project(socks5_proxy_handler
	DESCRIPTION "SOCKS5 Proxy client handler"
	LANGUAGES CXX)

add_library(${PROJECT_NAME} STATIC src/${PROJECT_NAME}.cpp)
set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 17)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)

add_executable(test_${PROJECT_NAME} src/test_${PROJECT_NAME}.cpp)
target_link_libraries(test_${PROJECT_NAME} ${PROJECT_NAME})

