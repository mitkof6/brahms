add_library(resample_numeric SHARED resample_numeric.cpp)
set_target_properties(resample_numeric PROPERTIES OUTPUT_NAME "component" PREFIX "")
if(APPLE)
target_link_libraries(resample_numeric brahms-engine brahms-engine-base)
endif(APPLE)

if(STANDALONE_INSTALL)
  set(COMP_PATH SystemML/Namespace/std/2009/resample/numeric)
else()
  set(COMP_PATH var/SystemML/Namespace/std/2009/resample/numeric)
endif()

install(TARGETS resample_numeric DESTINATION ${COMP_PATH}/brahms/0)
install(FILES ${CMAKE_SOURCE_DIR}/shared/1199/release.xml DESTINATION ${COMP_PATH}/brahms/0)
install(FILES ${CMAKE_SOURCE_DIR}/shared/process/node.xml DESTINATION ${COMP_PATH})
