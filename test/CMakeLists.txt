add_subdirectory(googletest)

add_executable(unit_test ahandler_test.cpp amessage_test.cpp)
target_link_libraries(unit_test PRIVATE aloop gtest_main)