---
UID: TP:sensors
ms.assetid: 8a7a095d-53d4-30a8-a1d2-4ef29c8a344d
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Sensors


Overview of the Sensors technology.

To develop Sensors, you need these headers:

 * [gnssdriver.h](..\gnssdriver\index.md)
 * [sensorsclassextension.h](..\sensorsclassextension\index.md)
 * [sensorscx.h](..\sensorscx\index.md)
 * [sensorsdef.h](..\sensorsdef\index.md)

For the programming guide, see [Sensors](https://docs.microsoft.com/en-us/windows-hardware/drivers/sensors).

This section contains reference information for  sensor and GNSS device driver DDIs.

## Sensor device driver reference for Windows 8.1

In Windows 8.1,  COM interfaces and other constructs for Windows sensor user-mode drivers are built on the Windows Driver Frameworks (WDF) - User-Mode Driver Framework (UMDF) platform. The sensor interface that is used by drivers is ISensorClassExtension. The sensor interface that is implemented by drivers is the ISensorDriver. These APIs are in the following headers:

- SensorsClassExtension.h
- Sensors.h

## Sensor device driver reference for Windows 10

 Sensors class extension v2 is designed for use by driver developers who work on sensor drivers for Windows 10 and newer operating systems. The associated APIs are in the following header files:

- Sensorsdef.h
- SensorCx.h

Send comments about this topic to Microsoft

