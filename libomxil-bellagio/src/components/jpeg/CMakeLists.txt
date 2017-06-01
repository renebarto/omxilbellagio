project(libomxjpeg.la)

add_subdirectory(libjpeg-6c)

set(COMPILER_DEFINES
    )
set(COMPILER_FLAGS
    -Werror -pthread -Wall -Wno-error=switch -fPIC -DPIC)
set(INCLUDE_DIRS
    . ../../.. ../.. .. ../../../include ../../base ./libjpeg-6c)
set(LIBS
    asound libomx-bellagio)

set(OMX_JPEGDEC_COMPONENT_SOURCE_FILES
    omx_jpegdec_component.c
    )
set(OMX_JPEGDEC_COMPONENT_HEADER_FILES

    omx_jpegdec_component.h)
set(OMX_JPEGDEC_COMPONENT_OBJECT
    libomxjpeg_la-omx_jpegdec_component.lo)

add_library(${OMX_JPEGDEC_COMPONENT_OBJECT} OBJECT ${OMX_JPEGDEC_COMPONENT_SOURCE_FILES} ${OMX_JPEGDEC_COMPONENT_HEADER_FILES})
target_compile_definitions(${OMX_JPEGDEC_COMPONENT_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${OMX_JPEGDEC_COMPONENT_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${OMX_JPEGDEC_COMPONENT_OBJECT} PRIVATE ${INCLUDE_DIRS})

set(OMX_JPEGENC_COMPONENT_SOURCE_FILES
    omx_jpegenc_component.c
    )
set(OMX_JPEGENC_COMPONENT_HEADER_FILES

    omx_jpegenc_component.h)
set(OMX_JPEGENC_COMPONENT_OBJECT
    libomxjpeg_la-omx_jpegenc_component.lo)

add_library(${OMX_JPEGENC_COMPONENT_OBJECT} OBJECT ${OMX_JPEGENC_COMPONENT_SOURCE_FILES} ${OMX_JPEGENC_COMPONENT_HEADER_FILES})
target_compile_definitions(${OMX_JPEGENC_COMPONENT_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${OMX_JPEGENC_COMPONENT_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${OMX_JPEGENC_COMPONENT_OBJECT} PRIVATE ${INCLUDE_DIRS})

set(RDBMP_SOURCE_FILES
    rdbmp.c
    )
set(RDBMP_HEADER_FILES
    )
set(RDBMP_OBJECT
    libomxjpeg_la-rdbmp.lo)

add_library(${RDBMP_OBJECT} OBJECT ${RDBMP_SOURCE_FILES} ${RDBMP_HEADER_FILES})
target_compile_definitions(${RDBMP_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${RDBMP_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${RDBMP_OBJECT} PRIVATE ${INCLUDE_DIRS})

set(WRBMP_SOURCE_FILES
    wrbmp.c
    )
set(WRBMP_HEADER_FILES
    )
set(WRBMP_OBJECT
    libomxjpeg_la-wrbmp.lo)

add_library(${WRBMP_OBJECT} OBJECT ${WRBMP_SOURCE_FILES} ${WRBMP_HEADER_FILES})
target_compile_definitions(${WRBMP_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${WRBMP_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${WRBMP_OBJECT} PRIVATE ${INCLUDE_DIRS})

set(LIBRARY_ENTRY_POINT_SOURCE_FILES
    library_entry_point.c
    )
set(LIBRARY_ENTRY_POINT_HEADER_FILES

    )
set(LIBRARY_ENTRY_POINT_OBJECT
    libomxjpeg_la-library_entry_point.lo)

add_library(${LIBRARY_ENTRY_POINT_OBJECT} OBJECT ${LIBRARY_ENTRY_POINT_SOURCE_FILES} ${LIBRARY_ENTRY_POINT_HEADER_FILES})
target_compile_definitions(${LIBRARY_ENTRY_POINT_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${LIBRARY_ENTRY_POINT_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${LIBRARY_ENTRY_POINT_OBJECT} PRIVATE ${INCLUDE_DIRS})

add_library(${PROJECT_NAME} STATIC
    $<TARGET_OBJECTS:${OMX_JPEGDEC_COMPONENT_OBJECT}>
    $<TARGET_OBJECTS:${OMX_JPEGENC_COMPONENT_OBJECT}>
    $<TARGET_OBJECTS:${LIBRARY_ENTRY_POINT_OBJECT}>
    )
target_compile_definitions(${PROJECT_NAME} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${PROJECT_NAME} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${PROJECT_NAME} PRIVATE ${INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME} PRIVATE ${LIBS})
add_dependencies(${PROJECT_NAME} omxil-bellagio libjpeg-6c.la)