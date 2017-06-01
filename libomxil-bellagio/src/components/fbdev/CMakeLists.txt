project(libomxfbdev.la)

set(COMPILER_DEFINES
    )
set(COMPILER_FLAGS
    -Werror -pthread -Wall -Wno-error=switch -fPIC -DPIC)
set(INCLUDE_DIRS
    . ../../.. ../.. .. ../../../include ../../base)
set(LIBS
    asound libomx-bellagio)

set(OMX_FBDEV_SINK_COMPONENT_SOURCE_FILES
    omx_fbdev_sink_component.c
    )
set(OMX_FBDEV_SINK_COMPONENT_HEADER_FILES
    ../../../src/omxcore.h
    ../../../include/OMX_Component.h
    ../../../include/OMX_Audio.h
    ../../../include/OMX_Core.h
    ../../../include/OMX_Index.h
    ../../../include/OMX_Types.h
    ../../../include/OMX_Video.h
    ../../../include/OMX_IVCommon.h
    ../../../include/OMX_Image.h
    ../../../include/OMX_Other.h
    ../../../src/component_loader.h
    ../../../src/omx_comp_debug_levels.h
    omx_fbdev_sink_component.h
    ../../../src/base/omx_base_video_port.h
    ../../../src/base/omx_classmagic.h
    ../../../src/base/omx_base_port.h
    ../../../src/tsemaphore.h
    ../../../src/queue.h
    ../../../src/base/omx_base_clock_port.h
    ../../../src/base/omx_base_sink.h
    ../../../src/base/omx_base_component.h)
set(OMX_FBDEV_SINK_COMPONENT_OBJECT
    libomxfbdev_la-omx_fbdev_sink_component.lo)

add_library(${OMX_FBDEV_SINK_COMPONENT_OBJECT} OBJECT ${OMX_FBDEV_SINK_COMPONENT_SOURCE_FILES} ${OMX_FBDEV_SINK_COMPONENT_HEADER_FILES})
target_compile_definitions(${OMX_FBDEV_SINK_COMPONENT_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${OMX_FBDEV_SINK_COMPONENT_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${OMX_FBDEV_SINK_COMPONENT_OBJECT} PRIVATE ${INCLUDE_DIRS})

set(OMX_VIDEO_SCHEDULER_COMPONENT_SOURCE_FILES
    omx_video_scheduler_component.c
    )
set(OMX_VIDEO_SCHEDULER_COMPONENT_HEADER_FILES
    ../../../src/omxcore.h
    ../../../include/OMX_Component.h
    ../../../include/OMX_Audio.h
    ../../../include/OMX_Core.h
    ../../../include/OMX_Index.h
    ../../../include/OMX_Types.h
    ../../../include/OMX_Video.h
    ../../../include/OMX_IVCommon.h
    ../../../include/OMX_Image.h
    ../../../include/OMX_Other.h
    ../../../src/component_loader.h
    ../../../src/omx_comp_debug_levels.h
    omx_video_scheduler_component.h
    ../../../src/base/omx_base_filter.h
    ../../../src/base/omx_base_component.h
    ../../../src/tsemaphore.h
    ../../../src/queue.h
    ../../../src/base/omx_classmagic.h
    ../../../src/base/omx_base_port.h
    ../../../src/base/omx_base_video_port.h
    ../../../src/base/omx_base_clock_port.h)
set(OMX_VIDEO_SCHEDULER_COMPONENT_OBJECT
    libomxfbdev_la-omx_video_scheduler_component.lo)

add_library(${OMX_VIDEO_SCHEDULER_COMPONENT_OBJECT} OBJECT ${OMX_VIDEO_SCHEDULER_COMPONENT_SOURCE_FILES} ${OMX_VIDEO_SCHEDULER_COMPONENT_HEADER_FILES})
target_compile_definitions(${OMX_VIDEO_SCHEDULER_COMPONENT_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${OMX_VIDEO_SCHEDULER_COMPONENT_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${OMX_VIDEO_SCHEDULER_COMPONENT_OBJECT} PRIVATE ${INCLUDE_DIRS})

set(LIBRARY_ENTRY_POINT_SOURCE_FILES
    library_entry_point.c
    )
set(LIBRARY_ENTRY_POINT_HEADER_FILES
    ../../../src/st_static_component_loader.h
    ../../../src/omxcore.h
    ../../../include/OMX_Component.h
    ../../../include/OMX_Audio.h
    ../../../include/OMX_Core.h
    ../../../include/OMX_Index.h
    ../../../include/OMX_Types.h
    ../../../include/OMX_Video.h
    ../../../include/OMX_IVCommon.h
    ../../../include/OMX_Image.h
    ../../../include/OMX_Other.h
    ../../../src/component_loader.h
    ../../../src/omx_comp_debug_levels.h
    omx_fbdev_sink_component.h
    ../../../src/base/omx_base_video_port.h
    ../../../src/base/omx_classmagic.h
    ../../../src/base/omx_base_port.h
    ../../../src/tsemaphore.h
    ../../../src/queue.h
    ../../../src/base/omx_base_clock_port.h
    ../../../src/base/omx_base_sink.h
    ../../../src/base/omx_base_component.h
    omx_video_scheduler_component.h
    ../../../src/base/omx_base_filter.h)
set(LIBRARY_ENTRY_POINT_OBJECT
    libomxfbdev_la-library_entry_point.lo)

add_library(${LIBRARY_ENTRY_POINT_OBJECT} OBJECT ${LIBRARY_ENTRY_POINT_SOURCE_FILES} ${LIBRARY_ENTRY_POINT_HEADER_FILES})
target_compile_definitions(${LIBRARY_ENTRY_POINT_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${LIBRARY_ENTRY_POINT_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${LIBRARY_ENTRY_POINT_OBJECT} PRIVATE ${INCLUDE_DIRS})

add_library(${PROJECT_NAME} STATIC
    $<TARGET_OBJECTS:${OMX_FBDEV_SINK_COMPONENT_OBJECT}>
    $<TARGET_OBJECTS:${OMX_VIDEO_SCHEDULER_COMPONENT_OBJECT}>
    $<TARGET_OBJECTS:${LIBRARY_ENTRY_POINT_OBJECT}>)
target_compile_definitions(${PROJECT_NAME} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${PROJECT_NAME} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${PROJECT_NAME} PRIVATE ${INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME} PRIVATE ${LIBS})
add_dependencies(${PROJECT_NAME} omxil-bellagio)