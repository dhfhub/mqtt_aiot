file(GLOB SOURCES "*.c" "linux/*.c")

add_library(paho-embed-mqtt3cc SHARED ${SOURCES})

target_include_directories(paho-embed-mqtt3cc PRIVATE "linux")
target_link_libraries(paho-embed-mqtt3cc paho-embed-mqtt3c)
target_compile_definitions(paho-embed-mqtt3cc PRIVATE
             MQTTCLIENT_PLATFORM_HEADER=MQTTLinux.h MQTTCLIENT_QOS2=1)
