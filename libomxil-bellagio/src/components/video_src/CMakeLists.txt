project(libomxvideosrc.la)

set(COMPILER_DEFINES
    )
set(COMPILER_FLAGS
    -Werror -pthread -Wall -Wno-error=switch -Wno-error=unused-but-set-variable -fPIC -DPIC)
set(INCLUDE_DIRS
    . ../../.. ../.. .. ../../../include ../../base)
set(LIBS
    asound libomx-bellagio)

set(OMX_VIDEOSRC_COMPONENT_SOURCE_FILES
    omx_videosrc_component.c
    )
set(OMX_VIDEOSRC_COMPONENT_HEADER_FILES

    omx_videosrc_component.h)
set(OMX_VIDEOSRC_COMPONENT_OBJECT
    libomxvideosrc_la-omx_videosrc_component.lo)

add_library(${OMX_VIDEOSRC_COMPONENT_OBJECT} OBJECT ${OMX_VIDEOSRC_COMPONENT_SOURCE_FILES} ${OMX_VIDEOSRC_COMPONENT_HEADER_FILES})
target_compile_definitions(${OMX_VIDEOSRC_COMPONENT_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${OMX_VIDEOSRC_COMPONENT_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${OMX_VIDEOSRC_COMPONENT_OBJECT} PRIVATE ${INCLUDE_DIRS})

set(LIBRARY_ENTRY_POINT_SOURCE_FILES
    library_entry_point.c
    )
set(LIBRARY_ENTRY_POINT_HEADER_FILES
    )
set(LIBRARY_ENTRY_POINT_OBJECT
    libomxvideosrc_la-library_entry_point.lo)

add_library(${LIBRARY_ENTRY_POINT_OBJECT} OBJECT ${LIBRARY_ENTRY_POINT_SOURCE_FILES} ${LIBRARY_ENTRY_POINT_HEADER_FILES})
target_compile_definitions(${LIBRARY_ENTRY_POINT_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${LIBRARY_ENTRY_POINT_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${LIBRARY_ENTRY_POINT_OBJECT} PRIVATE ${INCLUDE_DIRS})

add_library(${PROJECT_NAME} STATIC
    $<TARGET_OBJECTS:${OMX_VIDEOSRC_COMPONENT_OBJECT}>
    $<TARGET_OBJECTS:${LIBRARY_ENTRY_POINT_OBJECT}>)
target_compile_definitions(${PROJECT_NAME} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${PROJECT_NAME} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${PROJECT_NAME} PRIVATE ${INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME} PRIVATE ${LIBS})
add_dependencies(${PROJECT_NAME} omxil-bellagio)