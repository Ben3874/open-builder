
add_library(ob-server
    scripting/server_game_data.cpp
    server_engine.cpp
    network/server.cpp
    world/terrain_generation.cpp
)

set_flags(ob-server)

# Link executable to the libraries
target_link_libraries(ob-server 
    glad
    ob-common
    lua
    Threads::Threads 
    ${SFML_LIBRARIES} 
    ${SFML_DEPENDENCIES}
    ${CMAKE_DL_LIBS}
)

target_include_directories(ob-common
PUBLIC
${SFML_INCLUDE_DIR}
)