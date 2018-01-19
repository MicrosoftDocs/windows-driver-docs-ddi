---
UID: NE:strmini._STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE
title: _STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE
author: windows-driver-content
description: .
old-location: stream\stream_minidriver_device_notification_type.htm
old-project: stream
ms.assetid: 34DAA236-ACD0-4C25-BB45-00A81D2F131D
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE, STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE, *PSTREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: strmini.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE
req.alt-loc: Strmini.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE, *PSTREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# _STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE enumeration



## -description




## -syntax

````
typedef enum _STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE { 
  ReadyForNextDeviceRequest,
  DeviceRequestComplete,
  SignalMultipleDeviceEvents,
  SignalDeviceEvent,
  DeleteDeviceEvent,
#if (NTDDI_VERSION >= NTDDI_WINXP)
  SignalMultipleDeviceInstanceEvents,
#endif 
  DeviceNotificationMaximum
} STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE, *PSTREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE;
````


## -enum-fields

### -field ReadyForNextDeviceRequest

Indicates that the minidriver is ready for the next device request.


### -field DeviceRequestComplete

Indicates that the specified device SRB has completed.


### -field SignalMultipleDeviceEvents


### -field SignalDeviceEvent


### -field DeleteDeviceEvent


### -field SignalMultipleDeviceInstanceEvents


### -field DeviceNotificationMaximum


## -remarks
