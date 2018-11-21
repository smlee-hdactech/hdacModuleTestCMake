project(hashes)

#add_library(${PROJECT_NAME} src/strcodeclib.cpp)
add_library(${PROJECT_NAME}
    SHARED
    src/crypto.cpp
    src/hmac_sha256.cpp
    src/hmac_sha512.cpp
    src/ripemd160.cpp
    src/sha1.cpp
    src/sha256.cpp
    src/sha512.cpp
    )

add_library(sub::hs ALIAS ${PROJECT_NAME})

target_include_directories(${PROJECT_NAME}
    PUBLIC
    ${PROJECT_SOURCE_DIR}/include)
#message("cmake source dir: "${PROJECT_SOURCE_DIR})
