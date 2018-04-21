add_executable (server main.cpp)
target_link_libraries (server ${Boost_LIBRARIES} ${CMAKE_THREAD_LIBS_INIT})
