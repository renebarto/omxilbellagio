project(omxbase)

set(COMPILER_DEFINES
    HAVE_CONFIG_H)
set(COMPILER_FLAGS
    -Werror -pthread -Wall -Wno-error=switch)
set(COMPILER_FLAGS_PIC
    -Werror -pthread -Wall -Wno-error=switch -fPIC -DPIC)
set(INCLUDE_DIRS
    . ../.. .. ../../include)
set(COMPONENT_SOURCE_FILES
    omx_base_component.c
    )
set(COMPONENT_HEADER_FILES
    ../../src/omxcore.h
    ../../include/OMX_Component.h
    ../../include/OMX_Audio.h
    ../../include/OMX_Core.h
    ../../include/OMX_Index.h
    ../../include/OMX_Types.h
    ../../include/OMX_Video.h
    ../../include/OMX_IVCommon.h
    ../../include/OMX_Image.h
    ../../include/OMX_Other.h
    ../../src/component_loader.h
    ../../src/omx_comp_debug_levels.h
    omx_base_component.h
    ../../src/tsemaphore.h
    ../../src/queue.h
    omx_classmagic.h
    omx_base_port.h)
set(COMPONENT_OBJECT
    omxbase-omx_base_component)
set(COMPONENT_OBJECT_PIC
    omxbase-omx_base_component_pic)

add_library(${COMPONENT_OBJECT} OBJECT ${COMPONENT_SOURCE_FILES} ${COMPONENT_HEADER_FILES})
target_compile_definitions(${COMPONENT_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${COMPONENT_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${COMPONENT_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${COMPONENT_OBJECT_PIC} OBJECT ${COMPONENT_SOURCE_FILES} ${COMPONENT_HEADER_FILES})
target_compile_definitions(${COMPONENT_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${COMPONENT_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${COMPONENT_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(PORT_SOURCE_FILES
    omx_base_port.c
    )
set(PORT_HEADER_FILES
    ../../src/omxcore.h
    ../../include/OMX_Component.h
    ../../include/OMX_Audio.h
    ../../include/OMX_Core.h
    ../../include/OMX_Index.h
    ../../include/OMX_Types.h
    ../../include/OMX_Video.h
    ../../include/OMX_IVCommon.h
    ../../include/OMX_Image.h
    ../../include/OMX_Other.h
    ../../src/component_loader.h
    ../../src/omx_comp_debug_levels.h
    omx_base_component.h
    ../../src/tsemaphore.h
    ../../src/queue.h
    omx_classmagic.h
    omx_base_port.h)
set(PORT_OBJECT
    omxbase-omx_base_port)
set(PORT_OBJECT_PIC
    omxbase-omx_base_port_pic)

add_library(${PORT_OBJECT} OBJECT ${PORT_SOURCE_FILES} ${PORT_HEADER_FILES})
target_compile_definitions(${PORT_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${PORT_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${PORT_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${PORT_OBJECT_PIC} OBJECT ${PORT_SOURCE_FILES} ${PORT_HEADER_FILES})
target_compile_definitions(${PORT_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${PORT_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${PORT_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(FILTER_SOURCE_FILES
    omx_base_filter.c
    )
set(FILTER_HEADER_FILES
    ../../src/omxcore.h
    ../../include/OMX_Component.h
    ../../include/OMX_Audio.h
    ../../include/OMX_Core.h
    ../../include/OMX_Index.h
    ../../include/OMX_Types.h
    ../../include/OMX_Video.h
    ../../include/OMX_IVCommon.h
    ../../include/OMX_Image.h
    ../../include/OMX_Other.h
    ../../src/component_loader.h
    ../../src/omx_comp_debug_levels.h
    omx_base_component.h
    ../../src/tsemaphore.h
    ../../src/queue.h
    omx_classmagic.h
    omx_base_port.h
    omx_base_filter.h)
set(FILTER_OBJECT
    omxbase-omx_base_filter)
set(FILTER_OBJECT_PIC
    omxbase-omx_base_filter_pic)

add_library(${FILTER_OBJECT} OBJECT ${FILTER_SOURCE_FILES} ${FILTER_HEADER_FILES})
target_compile_definitions(${FILTER_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${FILTER_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${FILTER_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${FILTER_OBJECT_PIC} OBJECT ${FILTER_SOURCE_FILES} ${FILTER_HEADER_FILES})
target_compile_definitions(${FILTER_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${FILTER_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${FILTER_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(SINK_SOURCE_FILES
    omx_base_sink.c
    )
set(SINK_HEADER_FILES
    ../../src/omxcore.h
    ../../include/OMX_Component.h
    ../../include/OMX_Audio.h
    ../../include/OMX_Core.h
    ../../include/OMX_Index.h
    ../../include/OMX_Types.h
    ../../include/OMX_Video.h
    ../../include/OMX_IVCommon.h
    ../../include/OMX_Image.h
    ../../include/OMX_Other.h
    ../../src/component_loader.h
    ../../src/omx_comp_debug_levels.h
    omx_base_component.h
    ../../src/tsemaphore.h
    ../../src/queue.h
    omx_classmagic.h
    omx_base_port.h
    omx_base_sink.h)
set(SINK_OBJECT
    omxbase-omx_base_sink)
set(SINK_OBJECT_PIC
    omxbase-omx_base_sink_pic)

add_library(${SINK_OBJECT} OBJECT ${SINK_SOURCE_FILES} ${SINK_HEADER_FILES})
target_compile_definitions(${SINK_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${SINK_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${SINK_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${SINK_OBJECT_PIC} OBJECT ${SINK_SOURCE_FILES} ${SINK_HEADER_FILES})
target_compile_definitions(${SINK_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${SINK_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${SINK_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(SOURCE_SOURCE_FILES
    omx_base_source.c
    )
set(SOURCE_HEADER_FILES
    ../../src/omxcore.h
    ../../include/OMX_Component.h
    ../../include/OMX_Audio.h
    ../../include/OMX_Core.h
    ../../include/OMX_Index.h
    ../../include/OMX_Types.h
    ../../include/OMX_Video.h
    ../../include/OMX_IVCommon.h
    ../../include/OMX_Image.h
    ../../include/OMX_Other.h
    ../../src/component_loader.h
    ../../src/omx_comp_debug_levels.h
    omx_base_component.h
    ../../src/tsemaphore.h
    ../../src/queue.h
    omx_classmagic.h
    omx_base_port.h
    omx_base_source.h)
set(SOURCE_OBJECT
    omxbase-omx_base_source)
set(SOURCE_OBJECT_PIC
    omxbase-omx_base_source_pic)

add_library(${SOURCE_OBJECT} OBJECT ${SOURCE_SOURCE_FILES} ${SOURCE_HEADER_FILES})
target_compile_definitions(${SOURCE_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${SOURCE_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${SOURCE_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${SOURCE_OBJECT_PIC} OBJECT ${SOURCE_SOURCE_FILES} ${SOURCE_HEADER_FILES})
target_compile_definitions(${SOURCE_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${SOURCE_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${SOURCE_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(AUDIO_PORT_SOURCE_FILES
    omx_base_audio_port.c
    )
set(AUDIO_PORT_HEADER_FILES
    ../../src/omxcore.h
    ../../include/OMX_Component.h
    ../../include/OMX_Audio.h
    ../../include/OMX_Core.h
    ../../include/OMX_Index.h
    ../../include/OMX_Types.h
    ../../include/OMX_Video.h
    ../../include/OMX_IVCommon.h
    ../../include/OMX_Image.h
    ../../include/OMX_Other.h
    ../../src/component_loader.h
    ../../src/omx_comp_debug_levels.h
    ../../src/tsemaphore.h
    ../../src/queue.h
    omx_classmagic.h
    omx_base_port.h
    omx_base_audio_port.h)
set(AUDIO_PORT_OBJECT
    omxbase-omx_base_audio_port)
set(AUDIO_PORT_OBJECT_PIC
    omxbase-omx_base_audio_port_pic)

add_library(${AUDIO_PORT_OBJECT} OBJECT ${AUDIO_PORT_SOURCE_FILES} ${AUDIO_PORT_HEADER_FILES})
target_compile_definitions(${AUDIO_PORT_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${AUDIO_PORT_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${AUDIO_PORT_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${AUDIO_PORT_OBJECT_PIC} OBJECT ${AUDIO_PORT_SOURCE_FILES} ${AUDIO_PORT_HEADER_FILES})
target_compile_definitions(${AUDIO_PORT_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${AUDIO_PORT_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${AUDIO_PORT_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(VIDEO_PORT_SOURCE_FILES
    omx_base_video_port.c
    )
set(VIDEO_PORT_HEADER_FILES
    ../../src/omxcore.h
    ../../include/OMX_Component.h
    ../../include/OMX_Audio.h
    ../../include/OMX_Core.h
    ../../include/OMX_Index.h
    ../../include/OMX_Types.h
    ../../include/OMX_Video.h
    ../../include/OMX_IVCommon.h
    ../../include/OMX_Image.h
    ../../include/OMX_Other.h
    ../../src/component_loader.h
    ../../src/omx_comp_debug_levels.h
    ../../src/tsemaphore.h
    ../../src/queue.h
    omx_classmagic.h
    omx_base_port.h
    omx_base_video_port.h)
set(VIDEO_PORT_OBJECT
    omxbase-omx_base_video_port)
set(VIDEO_PORT_OBJECT_PIC
    omxbase-omx_base_video_port_pic)

add_library(${VIDEO_PORT_OBJECT} OBJECT ${VIDEO_PORT_SOURCE_FILES} ${VIDEO_PORT_HEADER_FILES})
target_compile_definitions(${VIDEO_PORT_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${VIDEO_PORT_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${VIDEO_PORT_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${VIDEO_PORT_OBJECT_PIC} OBJECT ${VIDEO_PORT_SOURCE_FILES} ${VIDEO_PORT_HEADER_FILES})
target_compile_definitions(${VIDEO_PORT_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${VIDEO_PORT_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${VIDEO_PORT_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(IMAGE_PORT_SOURCE_FILES
    omx_base_image_port.c
    )
set(IMAGE_PORT_HEADER_FILES
    ../../src/omxcore.h
    ../../include/OMX_Component.h
    ../../include/OMX_Audio.h
    ../../include/OMX_Core.h
    ../../include/OMX_Index.h
    ../../include/OMX_Types.h
    ../../include/OMX_Video.h
    ../../include/OMX_IVCommon.h
    ../../include/OMX_Image.h
    ../../include/OMX_Other.h
    ../../src/component_loader.h
    ../../src/omx_comp_debug_levels.h
    ../../src/tsemaphore.h
    ../../src/queue.h
    omx_classmagic.h
    omx_base_port.h
    omx_base_image_port.h)
set(IMAGE_PORT_OBJECT
    omxbase-omx_base_image_port)
set(IMAGE_PORT_OBJECT_PIC
    omxbase-omx_base_image_port_pic)

add_library(${IMAGE_PORT_OBJECT} OBJECT ${IMAGE_PORT_SOURCE_FILES} ${IMAGE_PORT_HEADER_FILES})
target_compile_definitions(${IMAGE_PORT_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${IMAGE_PORT_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${IMAGE_PORT_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${IMAGE_PORT_OBJECT_PIC} OBJECT ${IMAGE_PORT_SOURCE_FILES} ${IMAGE_PORT_HEADER_FILES})
target_compile_definitions(${IMAGE_PORT_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${IMAGE_PORT_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${IMAGE_PORT_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(CLOCK_PORT_SOURCE_FILES
    omx_base_clock_port.c
    )
set(CLOCK_PORT_HEADER_FILES
    ../../src/omxcore.h
    ../../include/OMX_Component.h
    ../../include/OMX_Audio.h
    ../../include/OMX_Core.h
    ../../include/OMX_Index.h
    ../../include/OMX_Types.h
    ../../include/OMX_Video.h
    ../../include/OMX_IVCommon.h
    ../../include/OMX_Image.h
    ../../include/OMX_Other.h
    ../../src/component_loader.h
    ../../src/omx_comp_debug_levels.h
    ../../src/tsemaphore.h
    ../../src/queue.h
    omx_classmagic.h
    omx_base_port.h
    omx_base_clock_port.h)
set(CLOCK_PORT_OBJECT
    omxbase-omx_base_clock_port)
set(CLOCK_PORT_OBJECT_PIC
    omxbase-omx_base_clock_port_pic)

add_library(${CLOCK_PORT_OBJECT} OBJECT ${CLOCK_PORT_SOURCE_FILES} ${CLOCK_PORT_HEADER_FILES})
target_compile_definitions(${CLOCK_PORT_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${CLOCK_PORT_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${CLOCK_PORT_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${CLOCK_PORT_OBJECT_PIC} OBJECT ${CLOCK_PORT_SOURCE_FILES} ${CLOCK_PORT_HEADER_FILES})
target_compile_definitions(${CLOCK_PORT_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${CLOCK_PORT_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${CLOCK_PORT_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

add_library(${PROJECT_NAME} STATIC
    $<TARGET_OBJECTS:${COMPONENT_OBJECT_PIC}>
    $<TARGET_OBJECTS:${PORT_OBJECT_PIC}>
    $<TARGET_OBJECTS:${FILTER_OBJECT_PIC}>
    $<TARGET_OBJECTS:${SINK_OBJECT_PIC}>
    $<TARGET_OBJECTS:${SOURCE_OBJECT_PIC}>
    $<TARGET_OBJECTS:${AUDIO_PORT_OBJECT_PIC}>
    $<TARGET_OBJECTS:${VIDEO_PORT_OBJECT_PIC}>
    $<TARGET_OBJECTS:${IMAGE_PORT_OBJECT_PIC}>
    $<TARGET_OBJECTS:${CLOCK_PORT_OBJECT_PIC}>)
target_compile_definitions(${PROJECT_NAME} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${PROJECT_NAME} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${PROJECT_NAME} PRIVATE ${INCLUDE_DIRS})

message(STATUS "prefix ${CMAKE_INSTALL_PREFIX}")
install(TARGETS omxbase RUNTIME DESTINATION bin
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
    COMPONENT ${PROJECT_NAME})

configure_file(
    ${CMAKE_CURRENT_SOURCE_DIR}/uninstall.cmake.in
    ${CMAKE_CURRENT_BINARY_DIR}/uninstall.cmake
    IMMEDIATE @ONLY)

add_custom_target(uninstall_${PROJECT_NAME}
    COMMAND ${CMAKE_COMMAND} -DCOMPONENT=${PROJECT_NAME} -P ${CMAKE_CURRENT_BINARY_DIR}/uninstall.cmake
    COMMENT "Uninstalling ${PROJECT_NAME}")

add_custom_target(install_${PROJECT_NAME}
    COMMAND ${CMAKE_COMMAND} -DCOMPONENT=${PROJECT_NAME} -P ${CMAKE_BINARY_DIR}/cmake_install.cmake
    COMMENT "Installing ${PROJECT_NAME}")

add_dependencies(install_${PROJECT_NAME} ${PROJECT_NAME})
add_dependencies(install-components install_${PROJECT_NAME})
