add_executable(
  stdoutsubc
  stdoutsub.c
)

add_executable(
  aiot_c_demo
  aiot_c_demo.c
  aiot_mqtt_sign.c
)

target_link_libraries(stdoutsubc paho-embed-mqtt3cc paho-embed-mqtt3c)
target_include_directories(stdoutsubc PRIVATE "../mqtt.client" "../mqtt.client/linux")
target_compile_definitions(stdoutsubc PRIVATE MQTTCLIENT_PLATFORM_HEADER=MQTTLinux.h)

target_link_libraries(aiot_c_demo paho-embed-mqtt3cc paho-embed-mqtt3c)
target_include_directories(aiot_c_demo PRIVATE "../mqtt.client" "../mqtt.client/linux")
target_compile_definitions(aiot_c_demo PRIVATE MQTTCLIENT_PLATFORM_HEADER=MQTTLinux.h)
