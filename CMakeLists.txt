# CMakeList.txt: файл проекта CMake верхнего уровня; проведите глобальную конфигурацию
# и включите сюда подпроекты.
#
cmake_minimum_required (VERSION 3.8)

project ("CMakeProject1" LANGUAGES CUDA CXX)
# Включите подпроекты.
add_subdirectory ("CMakeProject1")
