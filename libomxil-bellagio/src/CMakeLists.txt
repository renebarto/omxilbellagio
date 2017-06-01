project(omxil-bellagio)

add_subdirectory(base)

set(COMPILER_DEFINES
    INSTALL_PATH_STR=\"/usr/local/lib/bellagio\")
set(COMPILER_FLAGS
    -Werror -pthread -Wall -Wno-error=switch)
set(COMPILER_FLAGS_PIC
    -Werror -pthread -Wall -Wno-error=switch -fPIC -DPIC)
set(INCLUDE_DIRS
    . .. ../include ./base)

set(ST_STATIC_COMPONENT_LOADER_SOURCE_FILES
    st_static_component_loader.c
    )
set(ST_STATIC_COMPONENT_LOADER_HEADER_FILES
    common.h
    st_static_component_loader.h
    omxcore.h
    ../include/OMX_Component.h
    ../include/OMX_Audio.h
    ../include/OMX_Core.h
    ../include/OMX_Index.h
    ../include/OMX_Types.h
    ../include/OMX_Video.h
     ../include/OMX_IVCommon.h
    ../include/OMX_Image.h
    ../include/OMX_Other.h
    component_loader.h
    omx_comp_debug_levels.h
    base/omx_base_component.h
    tsemaphore.h
    queue.h
    base/omx_classmagic.h
    base/omx_base_port.h)
set(ST_STATIC_COMPONENT_LOADER_OBJECT
    omxil_bellagio-st_static_component_loader)
set(ST_STATIC_COMPONENT_LOADER_OBJECT_PIC
    omxil_bellagio-st_static_component_loader_pic)

add_library(${ST_STATIC_COMPONENT_LOADER_OBJECT} OBJECT ${ST_STATIC_COMPONENT_LOADER_SOURCE_FILES} ${ST_STATIC_COMPONENT_LOADER_HEADER_FILES})
target_compile_definitions(${ST_STATIC_COMPONENT_LOADER_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${ST_STATIC_COMPONENT_LOADER_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${ST_STATIC_COMPONENT_LOADER_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${ST_STATIC_COMPONENT_LOADER_OBJECT_PIC} OBJECT ${ST_STATIC_COMPONENT_LOADER_SOURCE_FILES} ${ST_STATIC_COMPONENT_LOADER_HEADER_FILES})
target_compile_definitions(${ST_STATIC_COMPONENT_LOADER_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${ST_STATIC_COMPONENT_LOADER_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${ST_STATIC_COMPONENT_LOADER_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(OMXCORE_SOURCE_FILES
    omxcore.c
    )
set(OMXCORE_HEADER_FILES
    ../include/OMX_Core.h
    ../include/OMX_Index.h
    ../include/OMX_Types.h
    ../include/OMX_ContentPipe.h
    omxcore.h
    ../include/OMX_Component.h
    ../include/OMX_Audio.h
    ../include/OMX_Video.h
    ../include/OMX_IVCommon.h
    ../include/OMX_Image.h
    ../include/OMX_Other.h
    component_loader.h
    omx_comp_debug_levels.h
    omx_create_loaders.h)
set(OMXCORE_OBJECT
    omxil_bellagio-omxcore)
set(OMXCORE_OBJECT_PIC
    omxil_bellagio-omxcore_pic)

add_library(${OMXCORE_OBJECT} OBJECT ${OMXCORE_SOURCE_FILES} ${OMXCORE_HEADER_FILES})
target_compile_definitions(${OMXCORE_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${OMXCORE_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${OMXCORE_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${OMXCORE_OBJECT_PIC} OBJECT ${OMXCORE_SOURCE_FILES} ${OMXCORE_HEADER_FILES})
target_compile_definitions(${OMXCORE_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${OMXCORE_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${OMXCORE_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(OMX_CREATE_LOADERS_LINUX_SOURCE_FILES
    omx_create_loaders_linux.c
    )
set(OMX_CREATE_LOADERS_LINUX_HEADER_FILES
    component_loader.h
    ../include/OMX_Core.h
    ../include/OMX_Index.h
    ../include/OMX_Types.h
    omx_create_loaders.h
    st_static_component_loader.h
    omxcore.h
    ../include/OMX_Component.h
    ../include/OMX_Audio.h
    ../include/OMX_Video.h
    ../include/OMX_IVCommon.h
    ../include/OMX_Image.h
    ../include/OMX_Other.h
    common.h)
set(OMX_CREATE_LOADERS_LINUX_OBJECT
    omxil_bellagio-omx_create_loaders_linux)
set(OMX_CREATE_LOADERS_LINUX_OBJECT_PIC
    omxil_bellagio-omx_create_loaders_linux_pic)

add_library(${OMX_CREATE_LOADERS_LINUX_OBJECT} OBJECT ${OMX_CREATE_LOADERS_LINUX_SOURCE_FILES} ${OMX_CREATE_LOADERS_LINUX_HEADER_FILES})
target_compile_definitions(${OMX_CREATE_LOADERS_LINUX_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${OMX_CREATE_LOADERS_LINUX_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${OMX_CREATE_LOADERS_LINUX_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${OMX_CREATE_LOADERS_LINUX_OBJECT_PIC} OBJECT ${OMX_CREATE_LOADERS_LINUX_SOURCE_FILES} ${OMX_CREATE_LOADERS_LINUX_HEADER_FILES})
target_compile_definitions(${OMX_CREATE_LOADERS_LINUX_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${OMX_CREATE_LOADERS_LINUX_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${OMX_CREATE_LOADERS_LINUX_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(TSEMAPHORE_SOURCE_FILES
    tsemaphore.c
    )
set(TSEMAPHORE_HEADER_FILES
    tsemaphore.h omx_comp_debug_levels.h)
set(TSEMAPHORE_OBJECT
    omxil_bellagio-tsemaphore)
set(TSEMAPHORE_OBJECT_PIC
    omxil_bellagio-tsemaphore_pic)

add_library(${TSEMAPHORE_OBJECT} OBJECT ${TSEMAPHORE_SOURCE_FILES} ${TSEMAPHORE_HEADER_FILES})
target_compile_definitions(${TSEMAPHORE_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${TSEMAPHORE_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${TSEMAPHORE_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${TSEMAPHORE_OBJECT_PIC} OBJECT ${TSEMAPHORE_SOURCE_FILES} ${TSEMAPHORE_HEADER_FILES})
target_compile_definitions(${TSEMAPHORE_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${TSEMAPHORE_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${TSEMAPHORE_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(QUEUE_SOURCE_FILES
    queue.c
    )
set(QUEUE_HEADER_FILES
    queue.h omx_comp_debug_levels.h)
set(QUEUE_OBJECT
    omxil_bellagio-queue)
set(QUEUE_OBJECT_PIC
    omxil_bellagio-queue_pic)

add_library(${QUEUE_OBJECT} OBJECT ${QUEUE_SOURCE_FILES} ${QUEUE_HEADER_FILES})
target_compile_definitions(${QUEUE_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${QUEUE_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${QUEUE_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${QUEUE_OBJECT_PIC} OBJECT ${QUEUE_SOURCE_FILES} ${QUEUE_HEADER_FILES})
target_compile_definitions(${QUEUE_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${QUEUE_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${QUEUE_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(COMMON_SOURCE_FILES
    common.c
    )
set(COMMON_HEADER_FILES
    ../config.h common.h)
set(COMMON_OBJECT
    omxil_bellagio-common)
set(COMMON_OBJECT_PIC
    omxil_bellagio-common_pic)

add_library(${COMMON_OBJECT} OBJECT ${COMMON_SOURCE_FILES} ${COMMON_HEADER_FILES})
target_compile_definitions(${COMMON_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${COMMON_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${COMMON_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${COMMON_OBJECT_PIC} OBJECT ${COMMON_SOURCE_FILES} ${COMMON_HEADER_FILES})
target_compile_definitions(${COMMON_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${COMMON_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${COMMON_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(CONTENT_PIPE_INET_SOURCE_FILES
    content_pipe_inet.c
    )
set(CONTENT_PIPE_INET_HEADER_FILES
    content_pipe_inet.h ../include/OMX_Types.h ../include/OMX_ContentPipe.h omx_comp_debug_levels.h)
set(CONTENT_PIPE_INET_OBJECT
    omxil_bellagio-content_pipe_inet)
set(CONTENT_PIPE_INET_OBJECT_PIC
    omxil_bellagio-content_pipe_inet_pic)

add_library(${CONTENT_PIPE_INET_OBJECT} OBJECT ${CONTENT_PIPE_INET_SOURCE_FILES} ${CONTENT_PIPE_INET_HEADER_FILES})
target_compile_definitions(${CONTENT_PIPE_INET_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${CONTENT_PIPE_INET_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${CONTENT_PIPE_INET_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${CONTENT_PIPE_INET_OBJECT_PIC} OBJECT ${CONTENT_PIPE_INET_SOURCE_FILES} ${CONTENT_PIPE_INET_HEADER_FILES})
target_compile_definitions(${CONTENT_PIPE_INET_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${CONTENT_PIPE_INET_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${CONTENT_PIPE_INET_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(CONTENT_PIPE_FILE_SOURCE_FILES
    content_pipe_file.c
    )
set(CONTENT_PIPE_FILE_HEADER_FILES
    content_pipe_file.h ../include/OMX_Types.h ../include/OMX_ContentPipe.h omx_comp_debug_levels.h)
set(CONTENT_PIPE_FILE_OBJECT
    omxil_bellagio-content_pipe_file)
set(CONTENT_PIPE_FILE_OBJECT_PIC
    omxil_bellagio-content_pipe_file_pic)

add_library(${CONTENT_PIPE_FILE_OBJECT} OBJECT ${CONTENT_PIPE_FILE_SOURCE_FILES} ${CONTENT_PIPE_FILE_HEADER_FILES})
target_compile_definitions(${CONTENT_PIPE_FILE_OBJECT} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${CONTENT_PIPE_FILE_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${CONTENT_PIPE_FILE_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${CONTENT_PIPE_FILE_OBJECT_PIC} OBJECT ${CONTENT_PIPE_FILE_SOURCE_FILES} ${CONTENT_PIPE_FILE_HEADER_FILES})
target_compile_definitions(${CONTENT_PIPE_FILE_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${CONTENT_PIPE_FILE_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${CONTENT_PIPE_FILE_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(OMXREGISTER_SOURCE_FILES
    omxregister.c
    )
set(OMXREGISTER_HEADER_FILES
    ../include/OMX_Core.h
    ../include/OMX_Index.h
    ../include/OMX_Types.h
    ../include/OMX_ContentPipe.h
    omxcore.h
    ../include/OMX_Component.h
    ../include/OMX_Audio.h
    ../include/OMX_Video.h
    ../include/OMX_IVCommon.h
    ../include/OMX_Image.h
    ../include/OMX_Other.h
    component_loader.h
    omx_comp_debug_levels.h
    common.h)
set(OMXREGISTER_OBJECT
    omxregister_bellagio)
set(OMXREGISTER_OBJECT_PIC
    omxregister_bellagio_pic)

set(OMXREGISTER_BELLAGIO_DEFINES
    OMXILCOMPONENTSPATH=\"${plugindir}/\")
add_library(${OMXREGISTER_OBJECT} OBJECT ${OMXREGISTER_SOURCE_FILES} ${OMXREGISTER_HEADER_FILES})
target_compile_definitions(${OMXREGISTER_OBJECT} PRIVATE ${COMPILER_DEFINES} ${OMXREGISTER_BELLAGIO_DEFINES})
target_compile_options(${OMXREGISTER_OBJECT} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${OMXREGISTER_OBJECT} PRIVATE ${INCLUDE_DIRS})
add_library(${OMXREGISTER_OBJECT_PIC} OBJECT ${OMXREGISTER_SOURCE_FILES} ${OMXREGISTER_HEADER_FILES})
target_compile_definitions(${OMXREGISTER_OBJECT_PIC} PRIVATE ${COMPILER_DEFINES} ${OMXREGISTER_BELLAGIO_DEFINES})
target_compile_options(${OMXREGISTER_OBJECT_PIC} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${OMXREGISTER_OBJECT_PIC} PRIVATE ${INCLUDE_DIRS})

set(OMXIL_BELLAGIO_LINK_OPTIONS
    "-Wl,--whole-archive ${CMAKE_CURRENT_BINARY_DIR}/base/libomxbase.a -Wl,--no-whole-archive -ldl")
set(OMXIL_BELLAGIO_LIBS
    dl)
add_library(${PROJECT_NAME} STATIC
    $<TARGET_OBJECTS:${ST_STATIC_COMPONENT_LOADER_OBJECT_PIC}>
    $<TARGET_OBJECTS:${OMXCORE_OBJECT_PIC}>
    $<TARGET_OBJECTS:${OMX_CREATE_LOADERS_LINUX_OBJECT_PIC}>
    $<TARGET_OBJECTS:${TSEMAPHORE_OBJECT_PIC}>
    $<TARGET_OBJECTS:${COMMON_OBJECT_PIC}>
    $<TARGET_OBJECTS:${CONTENT_PIPE_INET_OBJECT_PIC}>
    $<TARGET_OBJECTS:${CONTENT_PIPE_FILE_OBJECT_PIC}>
    )
target_compile_definitions(${PROJECT_NAME} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${PROJECT_NAME} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${PROJECT_NAME} PRIVATE ${INCLUDE_DIRS})
#target_link_libraries(${PROJECT_NAME} PRIVATE ${OMXIL_BELLAGIO_LIBS})
set_target_properties(${PROJECT_NAME} PROPERTIES LINK_FLAGS ${OMXIL_BELLAGIO_LINK_OPTIONS})

add_library(${PROJECT_NAME}_SHARED SHARED
    $<TARGET_OBJECTS:${ST_STATIC_COMPONENT_LOADER_OBJECT_PIC}>
    $<TARGET_OBJECTS:${OMXCORE_OBJECT_PIC}>
    $<TARGET_OBJECTS:${OMX_CREATE_LOADERS_LINUX_OBJECT_PIC}>
    $<TARGET_OBJECTS:${TSEMAPHORE_OBJECT_PIC}>
    $<TARGET_OBJECTS:${COMMON_OBJECT_PIC}>
    $<TARGET_OBJECTS:${CONTENT_PIPE_INET_OBJECT_PIC}>
    $<TARGET_OBJECTS:${CONTENT_PIPE_FILE_OBJECT_PIC}>
    )
target_compile_definitions(${PROJECT_NAME}_SHARED PRIVATE ${COMPILER_DEFINES})
target_compile_options(${PROJECT_NAME}_SHARED PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${PROJECT_NAME}_SHARED PRIVATE ${INCLUDE_DIRS})
#target_link_libraries(${PROJECT_NAME}_SHARED PRIVATE ${OMXIL_BELLAGIO_LIBS})
set_target_properties(${PROJECT_NAME}_SHARED PROPERTIES LINK_FLAGS ${OMXIL_BELLAGIO_LINK_OPTIONS})
set_target_properties(${PROJECT_NAME}_SHARED PROPERTIES SOVERSION 0)
set_target_properties(${PROJECT_NAME}_SHARED PROPERTIES VERSION 0.0.0)
set_target_properties(${PROJECT_NAME}_SHARED PROPERTIES OUTPUT_NAME ${PROJECT_NAME})

add_dependencies(${PROJECT_NAME} omxbase)

set(plugindir ${CMAKE_INSTALL_PREFIX}/lib/bellagio)
set(OMXREGISTER_BELLAGIO_DEFINES
    OMXILCOMPONENTSPATH=\"/usr/local/lib/bellagio/\")
set(OMXREGISTER_BELLAGIO
    omxregister-bellagio)
set(OMXREGISTER_BELLAGIO_LIBS
    ${PROJECT_NAME} dl)
add_executable(${OMXREGISTER_BELLAGIO}
    $<TARGET_OBJECTS:${OMXREGISTER_OBJECT_PIC}>
    $<TARGET_OBJECTS:${COMMON_OBJECT_PIC}>)

target_compile_definitions(${OMXREGISTER_BELLAGIO} PRIVATE ${COMPILER_DEFINES} ${OMXREGISTER_BELLAGIO_DEFINES})
target_compile_options(${OMXREGISTER_BELLAGIO} PRIVATE ${COMPILER_FLAGS_PIC})
target_include_directories(${OMXREGISTER_BELLAGIO} PRIVATE ${INCLUDE_DIRS})
target_link_libraries(${OMXREGISTER_BELLAGIO} PRIVATE ${OMXREGISTER_BELLAGIO_LIBS})
set_target_properties(${OMXREGISTER_BELLAGIO} PROPERTIES LINK_FLAGS -Wl,-rpath,'\$ORIGIN/../lib/')

add_dependencies(${OMXREGISTER_BELLAGIO} ${PROJECT_NAME})

install(TARGETS ${PROJECT_NAME} RUNTIME DESTINATION bin
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
    COMPONENT ${PROJECT_NAME})

install(TARGETS ${OMXREGISTER_BELLAGIO} RUNTIME DESTINATION bin
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
    COMPONENT ${OMXREGISTER_BELLAGIO})

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

add_custom_target(uninstall_${OMXREGISTER_BELLAGIO}
    COMMAND ${CMAKE_COMMAND} -DCOMPONENT=${OMXREGISTER_BELLAGIO} -P ${CMAKE_CURRENT_BINARY_DIR}/uninstall.cmake
    COMMENT "Uninstalling ${OMXREGISTER_BELLAGIO}")

add_custom_target(install_${OMXREGISTER_BELLAGIO}
    COMMAND ${CMAKE_COMMAND} -DCOMPONENT=${OMXREGISTER_BELLAGIO} -P ${CMAKE_BINARY_DIR}/cmake_install.cmake
    COMMENT "Installing ${OMXREGISTER_BELLAGIO}")

add_dependencies(install_${PROJECT_NAME} ${PROJECT_NAME})
add_dependencies(install_${OMXREGISTER_BELLAGIO} ${OMXREGISTER_BELLAGIO})
add_dependencies(install-components install_${PROJECT_NAME})
add_dependencies(install-components install_${OMXREGISTER_BELLAGIO})

add_subdirectory(components)
