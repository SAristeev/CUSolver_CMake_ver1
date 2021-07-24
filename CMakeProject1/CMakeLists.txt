# CMakeList.txt: проект CMake для CMakeProject1; включите исходный код и определения,
# укажите здесь логику для конкретного проекта.
#
cmake_minimum_required (VERSION 3.8)

find_package(CUDAToolkit REQUIRED)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
# Добавьте источник в исполняемый файл этого проекта.

add_executable (CMakeProject1)
set_target_properties(CMakeProject1 PROPERTIES
    POSITION_INDEPENDENT_CODE ON)
target_sources(CMakeProject1 PRIVATE
	"${CMAKE_SOURCE_DIR}/CMakeProject1/CMakeProject1.cpp")
target_include_directories(CMakeProject1
	PRIVATE "${CMAKE_SOURCE_DIR}/utils")
target_include_directories(CMakeProject1 
	PRIVATE ${CMAKE_CUDA_TOOLKIT_INCLUDE_DIRECTORIES})
 target_link_libraries(CMakeProject1 PRIVATE CUDA::cudart CUDA::cusparse CUDA::cublas CUDA::cusolver)
 

# TODO: Добавьте тесты и целевые объекты, если это необходимо.
