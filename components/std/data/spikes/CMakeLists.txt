add_library(data_spikes SHARED data_spikes.cpp)
set_target_properties(data_spikes PROPERTIES OUTPUT_NAME "component" PREFIX "")
if(APPLE)
target_link_libraries(data_spikes brahms-engine brahms-engine-base)
endif(APPLE)

if(STANDALONE_INSTALL)
  set(COMP_PATH SystemML/Namespace/std/2009/data/spikes)
else()
  set(COMP_PATH var/SystemML/Namespace/std/2009/data/spikes)
endif()

install(TARGETS data_spikes DESTINATION ${COMP_PATH}/brahms/0)
install(FILES ${CMAKE_SOURCE_DIR}/shared/1199/release.xml DESTINATION ${COMP_PATH}/brahms/0)
install(FILES ${CMAKE_SOURCE_DIR}/shared/data/node.xml DESTINATION ${COMP_PATH})

# For legacy interface support need this installed in include/
install(FILES data_spikes.h DESTINATION ${INCLUDE_INSTALL_PATH})
