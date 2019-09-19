#set(Boost_USE_STATIC_LIBS        ON) # only find static libs
#set(Boost_USE_MULTITHREADED      ON)
#set(Boost_USE_STATIC_RUNTIME    OFF)
find_package(Boost COMPONENTS date_time filesystem system unit_test_framework REQUIRED)


if(Boost_FOUND)
    include_directories(${Boost_INCLUDE_DIRS})
    add_executable (Test test.cpp)
    target_link_libraries(Test ${Boost_LIBRARIES})
endif()

add_test(testesimples Test)