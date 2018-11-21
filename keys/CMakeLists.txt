project(keys)

#add_library(${PROJECT_NAME} src/strcodeclib.cpp)
add_library(${PROJECT_NAME}
    SHARED
    src/key.cpp
    src/keyslib.cpp
    src/pubkey.cpp
    src/utils/random.cpp
    src/utils/utiltime.cpp
    )

add_library(sub::ks ALIAS ${PROJECT_NAME})

target_include_directories(${PROJECT_NAME}
    PUBLIC
    ${PROJECT_SOURCE_DIR}/include
    ${bcstructs_SOURCE_DIR}/include
    ${hashes_SOURCE_DIR}/include
    )
#include_directories(${PROJECT_SOURCE_DIR}/include)

target_link_libraries(${PROJECT_NAME}
    sub::bcst
    )
#message("cmake source dir: "${PROJECT_SOURCE_DIR})
