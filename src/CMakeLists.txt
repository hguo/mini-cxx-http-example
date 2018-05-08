# add_executable (server main.cpp)
# target_link_libraries (server ${Boost_LIBRARIES} ${CMAKE_THREAD_LIBS_INIT})

add_library (zserver zserver.cpp)
target_link_libraries (zserver ${Boost_LIBRARIES} ${CMAKE_THREAD_LIBS_INIT})

add_executable (test_zserver main.c)
target_link_libraries (test_zserver zserver)

install (FILES zserver.h DESTINATION include)
install (TARGETS zserver DESTINATION lib)
install (TARGETS test_zserver DESTINATION bin)
