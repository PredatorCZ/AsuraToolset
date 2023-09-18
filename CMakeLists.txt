cmake_minimum_required(VERSION 3.3)

set(CMAKE_CXX_STANDARD 20)
project([PH]Toolset)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra -Wl,--no-undefined")

option(CLI "" ON)
# option(GLTF "" ON)

set(TPD_PATH ${CMAKE_CURRENT_SOURCE_DIR}/3rd_party)

add_subdirectory(${TPD_PATH}/spike)
include(version)
toolset_version()

set_target_properties(spike_cli PROPERTIES OUTPUT_NAME [PH]_toolset)

# add_spike_subdir(sample)
