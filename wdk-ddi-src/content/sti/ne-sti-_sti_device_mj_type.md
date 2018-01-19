---
UID: NE:sti._STI_DEVICE_MJ_TYPE
title: _STI_DEVICE_MJ_TYPE
author: windows-driver-content
description: The STI_DEVICE_TYPE type identifies the device type of a still image device.The DWORD is divided into a HIWORD containing the major device type, and a LOWORD containing a vendor-defined subtype.
old-location: image\sti_device_type.htm
old-project: image
ms.assetid: f5ab3aa3-c24e-4716-b94a-525c6b6776dc
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: _STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: sti.h
req.include-header: Sti.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STI_DEVICE_MJ_TYPE
req.alt-loc: Sti.h
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
req.typenames: STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# _STI_DEVICE_MJ_TYPE enumeration



## -description
The STI_DEVICE_TYPE type identifies the device type of a still image device.

The DWORD is divided into a HIWORD containing the major device type, and a LOWORD containing a vendor-defined subtype.



## -syntax

````
typedef enum _STI_DEVICE_MJ_TYPE { 
  StiDeviceTypeDefault         = 0,
  StiDeviceTypeScanner         = 1,
  StiDeviceTypeDigitalCamera   = 2,
  StiDeviceTypeStreamingVideo  = 3
} STI_DEVICE_MJ_TYPE;
````


## -enum-fields

### -field StiDeviceTypeDefault

Default type.


### -field StiDeviceTypeScanner

Scanner.


### -field StiDeviceTypeDigitalCamera

Digital camera.


### -field StiDeviceTypeStreamingVideo

Streaming video.


## -remarks
The following macros are used to extract the major device type and subtype:</p>