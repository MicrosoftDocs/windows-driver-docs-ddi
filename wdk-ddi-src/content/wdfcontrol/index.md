---
UID: NA:wdfcontrol
ms.assetid: df09b3f6-ec88-3410-a704-7ca8e681720e
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdfcontrol.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfcontrol.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WdfControlDeviceInitAllocate function](nf-wdfcontrol-wdfcontroldeviceinitallocate.md) | The WdfControlDeviceInitAllocate method allocates a WDFDEVICE_INIT structure that a driver uses when creating a new control device object. |
| [WdfControlDeviceInitSetShutdownNotification function](nf-wdfcontrol-wdfcontroldeviceinitsetshutdownnotification.md) | The WdfControlDeviceInitSetShutdownNotification method sets shutdown notification information for a control device object. |
| [WdfControlFinishInitializing function](nf-wdfcontrol-wdfcontrolfinishinitializing.md) | The WdfControlFinishInitializing method informs the framework that a driver has finished initializing a specified control device object. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_WDF_DEVICE_SHUTDOWN_FLAGS enumeration](ne-wdfcontrol-_wdf_device_shutdown_flags.md) | The WDF_DEVICE_SHUTDOWN_FLAGS enumeration defines flags that identify types of shutdown notifications that a driver can receive. |
