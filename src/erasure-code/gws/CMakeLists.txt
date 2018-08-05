# gws plugin

set(gws_srcs
  ErasureCodePluginGWS.cc
  ErasureCodeGWS.cc
  $<TARGET_OBJECTS:erasure_code_objs>
  $<TARGET_OBJECTS:crush_objs>
  ${CMAKE_SOURCE_DIR}/src/common/str_map.cc
)

add_library(ec_gws SHARED ${gws_srcs})
set_target_properties(ec_gws PROPERTIES
  INSTALL_RPATH "")
target_link_libraries(ec_gws json_spirit)
install(TARGETS ec_gws DESTINATION ${erasure_plugin_dir})
