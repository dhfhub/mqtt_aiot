cmake_minimum_required(VERSION 2.8)
project("mqttclient" C)

message(STATUS "CMake version: " ${CMAKE_VERSION})
message(STATUS "CMake system name: " ${CMAKE_SYSTEM_NAME})
string(TIMESTAMP BUILD_TIMESTAMP UTC)
message(STATUS "Timestamp is ${BUILD_TIMESTAMP}")

include_directories(mqtt.packet mqtt.client mqtt.client/linux mqtt.app)

#ADD_SUBDIRECTORY(mqtt.app)
#ADD_SUBDIRECTORY(mqtt.client)
#ADD_SUBDIRECTORY(mqtt.packet)

