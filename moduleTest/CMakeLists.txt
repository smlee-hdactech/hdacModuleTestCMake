project(moduleTest)

find_package (Boost 1.55.0 REQUIRED COMPONENTS system thread)
include_directories( ${Boost_INCLUDE_DIR} )
link_directories( ${Boost_LIBRARY_DIRS} )
set( Boost_USE_STATIC_LIBS        OFF )
set( Boost_USE_MULTITHREADED      ON )
set( Boost_USE_STATIC_RUNTIME     OFF )
set( BOOST_ALL_DYN_LINK           ON )

include(FindPkgConfig)
pkg_check_modules (SECP256K1 REQUIRED libsecp256k1)
pkg_check_modules (OPENSSL REQUIRED openssl)
pkg_check_modules (JSONSPIRIT REQUIRED json_spirit)

add_executable(${PROJECT_NAME} main.cpp)
target_include_directories(${PROJECT_NAME}
    PUBLIC
    ${rpccall_SOURCE_DIR}/include
    ${bcstructs_SOURCE_DIR}/include
    ${hashes_SOURCE_DIR}/include
    ${keys_SOURCE_DIR}/include
    ${strcodec_SOURCE_DIR}/include
    )

target_link_libraries(${PROJECT_NAME}
    rpccall
    bcstructs
    hashes
    keys
    strcodec
    ${Boost_LIBRARIES}
    ${SECP256K1_LIBRARIES}
    ${OPENSSL_LIBRARIES}
    )
#message("cmake source dir: "${PROJECT_SOURCE_DIR})
