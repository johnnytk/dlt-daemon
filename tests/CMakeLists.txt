# Setup testing
enable_testing()
include_directories(${gtest_SOURCE_DIR}/include)

configure_file(${CMAKE_SOURCE_DIR}/tests/testfile.dlt ${PROJECT_BINARY_DIR}/tests COPYONLY)
configure_file(${CMAKE_SOURCE_DIR}/tests/testfilter.txt ${PROJECT_BINARY_DIR}/tests COPYONLY)

add_executable(gtest_dlt_common gtest_dlt_common.cpp)
add_executable(gtest_dlt_user gtest_dlt_user.cpp)
target_link_libraries(gtest_dlt_common gtest gtest_main dlt)
target_link_libraries(gtest_dlt_user gtest gtest_main dlt)