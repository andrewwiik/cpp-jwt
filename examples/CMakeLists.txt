
include_directories(${OPENSSL_INCLUDE_DIR})

SET(CERT_ROOT_DIR "${CMAKE_CURRENT_SOURCE_DIR}/rsa_256")
SET(CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} -DCERT_ROOT_DIR=\"\\\"${CERT_ROOT_DIR}\\\"\"")

add_executable(simple_ex1 simple_ex1.cc)
target_link_libraries(simple_ex1 ${OPENSSL_LIBRARIES} ${GTEST_LIBRARIES})
add_test(NAME simple_ex1 COMMAND ./simple_ex1 WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR})

add_executable(simple_ex2 simple_ex2.cc)
target_link_libraries(simple_ex2 ${OPENSSL_LIBRARIES} ${GTEST_LIBRARIES})
add_test(NAME simple_ex2 COMMAND ./simple_ex2 WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR})

add_executable(simple_ex3_rsa simple_ex3_rsa.cc)
target_link_libraries(simple_ex3_rsa ${OPENSSL_LIBRARIES} ${GTEST_LIBRARIES})
add_test(NAME simple_ex3_rsa COMMAND ./simple_ex3_rsa WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR})

