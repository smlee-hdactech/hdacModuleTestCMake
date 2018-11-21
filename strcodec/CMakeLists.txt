project(strcodec)

#add_library(${PROJECT_NAME} src/strcodeclib.cpp)
add_library(${PROJECT_NAME} SHARED src/strcodeclib.cpp)
add_library(sub::scd ALIAS ${PROJECT_NAME})

target_include_directories(${PROJECT_NAME}
    PUBLIC
    ${PROJECT_SOURCE_DIR}/include)
#message("cmake source dir: "${PROJECT_SOURCE_DIR})
