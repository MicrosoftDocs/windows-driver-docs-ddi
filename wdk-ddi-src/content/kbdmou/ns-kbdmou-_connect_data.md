---
UID: NS:kbdmou._CONNECT_DATA
title: _CONNECT_DATA
author: windows-driver-content
description: CONNECT_DATA specifies information that Kbdclass and Mouclass use to connect to a keyboard or mouse port.
old-location: hid\connect_data__kbdclass_.htm
old-project: hid
ms.assetid: 8fdb5b1d-bbdb-4774-875a-7cdd047286f5
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _CONNECT_DATA, CONNECT_DATA, *PCONNECT_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: kbdmou.h
req.include-header: Kbdmou.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CONNECT_DATA
req.alt-loc: kbdmou.h
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
req.typenames: CONNECT_DATA, *PCONNECT_DATA
---

# _CONNECT_DATA structure



## -description
CONNECT_DATA specifies information that Kbdclass and Mouclass use to connect to a keyboard or mouse port.



## -syntax

````
typedef struct _CONNECT_DATA {
  PDEVICE_OBJECT ClassDeviceObject;
  PVOID          ClassService;
} CONNECT_DATA, *PCONNECT_DATA;
````


## -struct-fields

### -field ClassDeviceObject

Pointer to an upper-level class <a href="wdkgloss.f#wdkgloss.filter_device_object#wdkgloss.filter_device_object"><i>filter device object</i></a> (filter DO).


### -field ClassService

Specifies the class service routine. See  <a href="..\kbdmou\nc-kbdmou-pservice_callback_routine.md">PSERVICE_CALLBACK_ROUTINE</a>.


## -remarks
The keyboard class driver uses this structure with an <a href="..\kbdmou\ni-kbdmou-ioctl_internal_keyboard_connect.md">IOCTL_INTERNAL_KEYBOARD_CONNECT</a> request; the mouse class driver uses <a href="..\kbdmou\ni-kbdmou-ioctl_internal_mouse_connect.md">IOCTL_INTERNAL_MOUSE_CONNECT</a> .</p>