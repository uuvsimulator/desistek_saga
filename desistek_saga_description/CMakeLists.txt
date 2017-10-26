cmake_minimum_required(VERSION 2.8.3)
project(desistek_saga_description)

find_package(catkin REQUIRED)

catkin_package()

install(DIRECTORY mesh robots urdf launch
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
        PATTERN "*~" EXCLUDE)

if(CATKIN_ENABLE_TESTING)
  find_package(rostest REQUIRED)

  foreach(TEST_LAUNCHERS
    test/test_desistek_saga_model.launch
    add_rostest(${TEST_LAUNCHERS}))
  endforeach()
endif()
