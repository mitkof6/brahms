add_library(random_numeric SHARED random_numeric.cpp)
set_target_properties(random_numeric PROPERTIES OUTPUT_NAME "component" PREFIX "")
if(APPLE)
target_link_libraries(random_numeric brahms-engine brahms-engine-base)
endif(APPLE)

if(STANDALONE_INSTALL)
  set(COMP_PATH SystemML/Namespace/std/2009/random/numeric)
else()
  set(COMP_PATH var/SystemML/Namespace/std/2009/random/numeric)
endif()

install(TARGETS random_numeric DESTINATION ${COMP_PATH}/brahms/0)
install(FILES ${CMAKE_SOURCE_DIR}/shared/1199/release.xml DESTINATION ${COMP_PATH}/brahms/0)
install(FILES ${CMAKE_SOURCE_DIR}/shared/process/node.xml DESTINATION ${COMP_PATH})
