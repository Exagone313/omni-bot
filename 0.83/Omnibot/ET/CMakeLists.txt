# Omnibot ET build

add_library(omnibot-et MODULE ${CMAKE_CURRENT_SOURCE_DIR}/ET_BatchBuild.cpp)
target_link_libraries(omnibot-et omni-shared omnibot-common)

set_target_properties(omnibot-et PROPERTIES
    PREFIX ""
    OUTPUT_NAME "omnibot_et${MODULE_SUFFIX}"
    # POSITION_INDEPENDENT_CODE ON
    # MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>"
)

if (WIN32)
    set_target_properties(omnibot-et PROPERTIES
            LIBRARY_OUTPUT_DIRECTORY ""
            LIBRARY_OUTPUT_DIRECTORY_DEBUG ""
            LIBRARY_OUTPUT_DIRECTORY_RELEASE ""
    )

endif ()
