cmake_minimum_required(VERSION 3.16)
project(system_monitor)

# Suppress warnings about the use of FindPythonInterp and FindPythonLibs in ros
cmake_policy(SET CMP0148 OLD) 

find_package(catkin)

catkin_package()

catkin_install_python(
  PROGRAMS
    bin/cpu_monitor.py
    bin/hdd_monitor.py
    bin/mem_monitor.py
    bin/net_monitor.py
    bin/ntp_monitor.py
  DESTINATION
    ${CATKIN_PACKAGE_BIN_DESTINATION}
)

install(
  DIRECTORY
    launch/
  DESTINATION
    ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch
)

install(
  DIRECTORY
    config/
  DESTINATION
    ${CATKIN_PACKAGE_SHARE_DESTINATION}/config
)

