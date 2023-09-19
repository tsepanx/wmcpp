cmake_minimum_required(VERSION 3.11)
set(TARGET_NAME wmcpp)
project(${TARGET_NAME})

# enable_testing()
# set(BUILD_TESTING ON)
#
# add_test(
#         NAME allTests
#         COMMAND ./tests
# )

set(CMAKE_CXX_STANDARD 20)

SET(GCC_COVERAGE_COMPILE_FLAGS "-g -Wall")
#SET(GCC_COVERAGE_LINK_FLAGS    "-lgcov")

add_definitions(${GCC_COVERAGE_COMPILE_FLAGS})

include_directories(.)

message(TARGET_NAME: ${TARGET_NAME})

add_executable(${TARGET_NAME}
        src/main.cpp
)

# add_executable(tests
#         src/tests.cpp
# )
# Google Tests
# target_link_libraries(tests                  gtest gmock pthread)
# target_link_libraries(tests                  ssl crypto rpmsign-external)
# target_link_libraries(tests                  stdc++fs)
# add_dependencies(tests ${TARGET_NAME})


# target_link_libraries(${TARGET_NAME} PUBLIC ssl crypto rpmsign-external)
#target_link_libraries(${TARGET_NAME} PUBLIC stdc++fs)
target_link_libraries(${TARGET_NAME} PUBLIC X11)

install(
        TARGETS ${TARGET_NAME}
        DESTINATION bin
)
