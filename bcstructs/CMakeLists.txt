project(bcstructs)

#add_library(${PROJECT_NAME} src/strcodeclib.cpp)
add_library(${PROJECT_NAME}
    SHARED
    src/hashes.cpp
    src/structs/hash.cpp
    src/structs/uint256.cpp
    src/utils/allocators.cpp
    )

add_library(sub::bcst ALIAS ${PROJECT_NAME})

target_include_directories(${PROJECT_NAME}
    PUBLIC
    ${PROJECT_SOURCE_DIR}/include
    ${strcodec_SOURCE_DIR}/include
    ${hashes_SOURCE_DIR}/include
    )
#include_directories(${PROJECT_SOURCE_DIR}/include)

target_link_libraries(${PROJECT_NAME}
    sub::scd
    sub::hs
    )
#message("cmake source dir: "${PROJECT_SOURCE_DIR})
