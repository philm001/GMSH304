# Gmsh - Copyright (C) 1997-2017 C. Geuzaine, J.-F. Remacle
#
# See the LICENSE.txt file for license information. Please report all
# bugs and problems to the public mailing list <gmsh@onelab.info>.

set(SRC  
  Gmsh.cpp
    GmshMessage.cpp
  gmshPopplerWrapper.cpp
  Context.cpp
  Options.cpp
  CommandLine.cpp
  OS.cpp
  OpenFile.cpp
  CreateFile.cpp
  VertexArray.cpp
  SmoothData.cpp
  Octree.cpp 
    OctreeInternals.cpp
  StringUtils.cpp
  ListUtils.cpp
  TreeUtils.cpp avl.cpp
  MallocUtils.cpp
  onelabUtils.cpp
  GamePad.cpp
  GmshRemote.cpp
  GmshAPI.cpp
)

if(ENABLE_ONELAB AND NOT ENABLE_ONELAB2)
  set(SRC
    ${SRC}
    gmshLocalNetworkClient.cpp)
endif(ENABLE_ONELAB AND NOT ENABLE_ONELAB2)

file(GLOB HDR RELATIVE ${CMAKE_CURRENT_SOURCE_DIR} *.h) 
append_gmsh_src(Common "${SRC};${HDR}")
