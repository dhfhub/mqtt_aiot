#source file var
file(GLOB SOURCES "*.c")

#add lib paho-embed-mqtt3c
add_library(paho-embed-mqtt3c SHARED ${SOURCES})
target_compile_definitions(paho-embed-mqtt3c PRIVATE MQTT_SERVER MQTT_CLIENT)

#add lib MQTTPacketClient
add_library(MQTTPacketClient SHARED MQTTFormat MQTTPacket
            MQTTSerializePublish MQTTDeserializePublish
            MQTTConnectClient MQTTSubscribeClient MQTTUnsubscribeClient)
target_compile_definitions(MQTTPacketClient PRIVATE MQTT_CLIENT)

#add lib MQTTPacketServer
add_library(MQTTPacketServer SHARED MQTTFormat MQTTPacket
            MQTTSerializePublish MQTTDeserializePublish
            MQTTConnectServer MQTTSubscribeServer MQTTUnsubscribeServer)
target_compile_definitions(MQTTPacketServer PRIVATE MQTT_SERVER)
