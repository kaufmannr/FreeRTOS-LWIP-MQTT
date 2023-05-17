# FreeRTOS-LWIP-MQTT IoT
MQTT client based on FreeRTOS coreMQTT that uses a transparent transport layer which can be used with any physical transport interface.

## Who does need this?
Anyone using a LWIP based network stack who wants to build a scalable, reliable and high-performace IoT device.

## Why is this needed?
LWIP (current release 2.1.3) comes with an MQTT client example, which looks good at first glance. LWIP is integrated in many MCU software development kits, e.g. the NXP-SDK or some STM32 ODE Function Packs. However, I noticed that the LWIP MQTT client implementation has some severe drawbacks. Like beeing unable to send more than 64kB payloads, complicated usage with an RTOS, incomplete and faulty network error handling. Usage of an uncommon network API (altcp). Last but not least, poor performance.

All these points are fixed plus the ability, to develop your embedded application with full IoT communication on PC hardware.

This allows you to run the same code e.g. on the NXP iMX RT1062 and on Microsoft Windows and you can build, extend and debug your embedded application in Visual Studio without having an embedded hardware available. The modified MQTT code can be easily used with encryption (e.g. TLS).

The Windows FreeRTOS port is running on Windows as a process containing the FreeRTOS tasks as Windows threads plus a multimedia timer, which implementes the tick timer and can also be used to simulate interrupts down to 1ms intervals.

This MQTT client has been written to be used with FreeRTOS on an iMX RT1062 and Microsoft Windows. The transport layer is socket based, the Windows version uses the Windows sockets API, the iMX RT1062 code uses a patched (fixed) version of the LWIP stack in the NXP-SDK.
