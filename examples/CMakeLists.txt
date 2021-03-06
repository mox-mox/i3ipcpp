cmake_minimum_required(VERSION 3.0)
project(i3ipc++-examples)

include_directories(
	${I3IPCpp_INCLUDE_DIRS}
)

link_directories(
	${I3IPCpp_LIBRARY_DIRS}
)

#set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -Wall -Wextra -Wno-unused-parameter")
#set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -g3 -DDEBUG")
#set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -O2")



add_executable(workspaces workspaces.cpp)
target_link_libraries(workspaces ${I3IPCpp_LIBRARIES})

target_compile_options(workspaces
	PUBLIC -std=c++11 -Wall -Wextra -Wno-unused-parameter
	PUBLIC $<$<CONFIG:DEBUG>: -g3 -DDEBUG>
	PUBLIC $<$<CONFIG:RELEASE>: -O2>
)

add_executable(events events.cpp)
target_link_libraries(events ${I3IPCpp_LIBRARIES})

target_compile_options(events
	PUBLIC -std=c++11 -Wall -Wextra -Wno-unused-parameter
	PUBLIC $<$<CONFIG:DEBUG>: -g3 -DDEBUG>
	PUBLIC $<$<CONFIG:RELEASE>: -O2>
)


add_executable(bar-configs bar-configs.cpp)
target_link_libraries(bar-configs ${I3IPCpp_LIBRARIES})

target_compile_options(bar-configs
	PUBLIC -std=c++11 -Wall -Wextra -Wno-unused-parameter
	PUBLIC $<$<CONFIG:DEBUG>: -g3 -DDEBUG>
	PUBLIC $<$<CONFIG:RELEASE>: -O2>
)

