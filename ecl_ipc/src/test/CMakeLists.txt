###############################################################################
# Macros
###############################################################################

macro(ecl_ipc_add_gtest test_name)
  ament_add_gtest(ecl_test_${test_name} ${test_name}.cpp)
  if(TARGET ecl_test_${test_name})
    target_link_libraries(ecl_test_${test_name} ${PROJECT_NAME}
      ${ecl_build_LIBRARIES}
      ${ecl_config_LIBRARIES}
      ${ecl_errors_LIBRARIES}
      ${ecl_time_lite_LIBRARIES}
      ${ecl_exceptions_LIBRARIES}
      ${ecl_time_LIBRARIES}
    )
  endif()
endmacro()

###############################################################################
# Google Tests
###############################################################################

ecl_ipc_add_gtest(shared_memory)
ecl_ipc_add_gtest(semaphores)
ecl_ipc_add_gtest(semaphores_timed)

