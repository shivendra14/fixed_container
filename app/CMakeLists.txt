set(SHARED_FROZEN "${CMAKE_CURRENT_SOURCE_DIR}/../shared/frozen")
set(SHARED_PICOBENCH "${CMAKE_CURRENT_SOURCE_DIR}/../shared/picobench")

##############################
# CPP and Headers
##############################
file(GLOB_RECURSE gl_frozen ${SHARED_FROZEN}/frozen/*.h)

add_executable(
    FixedContainer
    ${gl_frozen}
    ${SHARED_PICOBENCH}/picobench.hpp
    main.cpp
)

##############################
# Include Paths
##############################
target_include_directories(FixedContainer PUBLIC "${SHARED_FROZEN}/")
target_include_directories(FixedContainer PUBLIC "${SHARED_PICOBENCH}/")