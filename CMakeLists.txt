cmake_minimum_required(VERSION 3.0)
project(CKMeans)
set(CMAKE_CXX_STANDARD 17)

add_library(CKMeans SHARED src/Ckmeans.1d.dp.cpp src/Ckmeans.1d.dp.h src/dynamic_prog.cpp
        src/fill_quadratic.cpp src/fill_log_linear.cpp src/select_levels.cpp src/weighted_select_levels.cpp
        src/EWL2_fill_SMAWK.cpp src/EWL2_dynamic_prog.cpp src/EWL2_fill_log_linear.cpp src/EWL2_fill_quadratic.cpp
        src/fill_SMAWK.cpp
        )
target_include_directories(CKMeans PUBLIC src)