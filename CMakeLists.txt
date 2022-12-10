cmake_minimum_required(VERSION 3.16.3...3.19.7 FATAL_ERROR)

project(ToolX)

#-----------------------------------------------------------------------------
# Extension meta-information
set(EXTENSION_HOMEPAGE "https://github.com/chir-set/ToolX/")
set(EXTENSION_CATEGORY "Vascular Modeling Toolkit")
set(EXTENSION_CONTRIBUTORS "Saleem Edah-Tally ([Surgeon] [Hobbyist developer])")
set(EXTENSION_DESCRIPTION "This extension aims at collecting C++ modules based on the VMTK libraries. Only one module is available now. Others may appear if clinical usefulness is found.")
set(EXTENSION_ICONURL "https://github.com/chir-set/ToolX/raw/master/ToolX.png")
set(EXTENSION_SCREENSHOTURLS "https://github.com/chir-set/ToolX/raw/master/BranchClipper/BranchClipper_0.png")
set(EXTENSION_DEPENDS "NA") # Specified as a list or "NA" if no dependencies

#-----------------------------------------------------------------------------
# Extension dependencies
find_package(Slicer REQUIRED)
include(${Slicer_USE_FILE})

find_package(VMTK REQUIRED)
include(${VMTK_USE_FILE})

#-----------------------------------------------------------------------------
# Extension modules
add_subdirectory(BranchClipper)
## NEXT_MODULE

#-----------------------------------------------------------------------------
include(${Slicer_EXTENSION_GENERATE_CONFIG})
include(${Slicer_EXTENSION_CPACK})
