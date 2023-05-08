# FreeRTOS-LWIP-MQTT
MQTT client based on FreeRTOS coreMQTT that uses a transparent transport layer which can be used with any physical transport interface.

This client has been written to be used with FreeRTOS on an iMX RT1062 and Microsoft Windows. The transport layer is socket based, the Windows version uses the Windows sockets API, the iMX RT1062 code uses a patched (fixed) version of the LWIP stack on the NXP-SDK.

This allows to run the same code on the iMX RT1062 and on Microsoft Windows and you can build, extend and debug your embedded application in Visual Studio without having an embedded hardware available. The modified MQTT code can be easily used with encryption (e.g. TLS).

The Windows FreeRTOS port is running on Windows as a process containing the FreeRTOS tasks as Windows threads plus a multimedia timer, which implementes the tick timer and can be used to simulate interrupts.
