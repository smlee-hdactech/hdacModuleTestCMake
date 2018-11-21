project(rpccall)

#add_library(${PROJECT_NAME} src/strcodeclib.cpp)
add_library(${PROJECT_NAME}
    SHARED
    src/cif_rpccall.cpp
    src/rpccaller.cpp
    src/rpc/rpcprotocol.cpp
    )

add_library(sub::rc ALIAS ${PROJECT_NAME})

target_include_directories(${PROJECT_NAME}
    PUBLIC
    ${PROJECT_SOURCE_DIR}/include
    ${strcodec_SOURCE_DIR}/include
    )
#include_directories(${PROJECT_SOURCE_DIR}/include)

target_link_libraries(${PROJECT_NAME}
    sub::scd)
message("cmake source dir: "${PROJECT_SOURCE_DIR})
message("strcodec source dir: "${strcodec_SOURCE_DIR})
