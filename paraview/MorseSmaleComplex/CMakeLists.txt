cmake_minimum_required(VERSION 2.4)

project(MorseSmaleComplex)

option(withParaView "Enable ParaView support" true)
set(withParaView true)

# path to the common code base
find_path(TTK_DIR ttk.cmake
  PATHS
    core/
    ../core/
    ../../core/
    ../../../core/
    sandbox/core/
    sandbox/../core/
    sandbox/../../core/
    sandbox/../../../core/
)
include(${TTK_DIR}/ttk.cmake)

# include the vtk wrapper for your TTK package 
ttk_add_vtkWrapper_package(vtkMorseSmaleComplex)

# Add the plugin
ttk_wrapup_paraview_plugin(
  MorseSmaleComplex
  1.0)
