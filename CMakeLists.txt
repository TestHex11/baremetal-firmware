cmake_minimum_required(VERSION 3.16)

project(baremetal_firmware
	VERSION 1.0.0
	LANGUAGES C CXX ASM
)

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_C_EXTENSIONS OFF)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Put firmware sources in src/ and public headers in include/.
file(GLOB_RECURSE FIRMWARE_SOURCES CONFIGURE_DEPENDS
	"${CMAKE_CURRENT_SOURCE_DIR}/src/*.c"
	"${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp"
	"${CMAKE_CURRENT_SOURCE_DIR}/src/*.s"
	"${CMAKE_CURRENT_SOURCE_DIR}/src/*.S"
)

if(FIRMWARE_SOURCES)
	add_executable(${PROJECT_NAME} ${FIRMWARE_SOURCES})
	target_include_directories(${PROJECT_NAME} PRIVATE
		"${CMAKE_CURRENT_SOURCE_DIR}/include"
        "${CMAKE_CURRENT_SOURCE_DIR}"
        "${CMAKE_CURRENT_SOURCE_DIR}/src"
        
	)
endif()
