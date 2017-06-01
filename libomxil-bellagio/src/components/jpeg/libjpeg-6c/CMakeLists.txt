project(libjpeg-6c.la)

set(COMPILER_DEFINES
    )
set(COMPILER_FLAGS
    -Werror -pthread -Wall -Wno-error=switch -fPIC -DPIC)
set(INCLUDE_DIRS
    . ../../.. ../.. .. ../../../include ../../base)
set(LIBS
    dl)

set(JPEG6C_LIB_SOURCE_FILES
    jcapimin.c jcapistd.c jccoefct.c jccolor.c jcdctmgr.c
    jchuff.c jcinit.c jcmainct.c jcmarker.c jcmaster.c jcomapi.c
    jcparam.c jcprepct.c jcsample.c jctrans.c jdapimin.c jdapistd.c
    jdatadst.c jdatasrc.c jdcoefct.c jdcolor.c jddctmgr.c jdhuff.c
    jdinput.c jdmainct.c jdmarker.c jdmaster.c jdmerge.c jdpostct.c
    jdsample.c jdtrans.c jerror.c jfdctflt.c jfdctfst.c jfdctint.c
    jidctflt.c jidctfst.c jidctint.c jquant1.c jquant2.c
    jutils.c jmemmgr.c jaricom.c jcarith.c jdarith.c)
set(JPEG6C_SYSDEP_SOURCES_FILES
    jmemansi.c)
set(JPEG6C_LIB_HEADER_FILES
    )

add_library(${PROJECT_NAME} STATIC
    ${JPEG6C_LIB_SOURCE_FILES}
    ${JPEG6C_SYSDEP_SOURCES_FILES}
    ${JPEG6C_LIB_HEADER_FILES}
    )
target_compile_definitions(${PROJECT_NAME} PRIVATE ${COMPILER_DEFINES})
target_compile_options(${PROJECT_NAME} PRIVATE ${COMPILER_FLAGS})
target_include_directories(${PROJECT_NAME} PRIVATE ${INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME} PRIVATE ${LIBS})
