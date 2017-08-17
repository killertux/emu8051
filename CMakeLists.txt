cmake_minimum_required(VERSION 2.6)
project(emu8051)
set(CURSES_NEED_NCURSES true)
find_package(Curses REQUIRED)

include_directories(${CURSES_INCLUDE_DIR} ${CMAKE_CURRENT_BINARY_DIR})

set(emu8051_SRCS
	core.c  
	disasm.c  
	emu.c  
	logicboard.c  
	mainview.c  
	memeditor.c  
	opcodes.c  
	options.c  
	popups.c
)

add_executable(emu8051 ${emu8051_SRCS})
target_link_libraries(emu8051 ${CURSES_LIBRARIES})

install(TARGETS emu8051 RUNTIME DESTINATION bin)
